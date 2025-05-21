---
layout: post
title: "Contributing to *GNOME Clocks*: \"Undo\" support for deleted alarms"
subtitle: "A small Vala patch that adds an **Undo** toast"
tags: [mac0470, usp, floss, software, GNOME, vala]
author: Augusto Mariano Bernardi
date: 2025-05-07
---


> **TL;DR**  
> Issue [**#359**](https://gitlab.gnome.org/GNOME/gnome-clocks/-/issues/359) asked for a way to undo an accidental alarm deletion.  
> Our merge request [!346](https://gitlab.gnome.org/GNOME/gnome-clocks/-/merge_requests/346) adds a toast that lets you restore the alarm with a single click.

---

## Why an “Undo” toast?

Deleting an alarm by mistake is surprisingly easy—one errant tap and the row disappears forever.  GNOME’s design guidelines recommend offering *lightweight, inline* undo options for potentially destructive actions.  A toast (`Adw.Toast`) is perfect: it appears for a few seconds, stays out of the way, and can host an **Undo** button.

---

## GitLab setup hiccups (a mini-postmortem)

1. **Fork refused to fork**  
   : My first click on “Fork” produced *“repository cannot be cloned”*. The root cause was that my **gitlab.gnome.org** account still pointed at a *detached* identity—GitLab.com thought I had 0 storage. Logging out, verifying my USP email and then signing back into the GNOME instance fixed it.

## The patch

<details>
<summary><code>src/alarm-face.vala</code> &nbsp;(+35&nbsp;-0)</summary>

```diff title="Add undo toast for alarm deletion"
@@
    private unowned Gtk.Stack stack;
    private Adw.Toast? ring_time_toast;
    private Alarm.Item? ring_time_toast_alarm;
+   private Adw.Toast? delete_toast;   // ⇽ new toast for “Undo”
+   private Alarm.Item? deleted_alarm; // ⇽ keeps a reference to the alarm we just removed
@@
            row.remove_alarm.connect (() => {
+               deleted_alarm = (Item) item;               // remember what we deleted
                alarms.delete_item ((Item) item);
                if (ring_time_toast != null && item == ring_time_toast_alarm) {
                    ring_time_toast_alarm = null;
                    ring_time_toast.dismiss ();
                }
+               show_delete_toast ();                       // ⇽ pop the toast
                save ();
            });
@@
        window.add_toast (ring_time_toast);
    }

+   // ---------- new helper ----------
+   private void show_delete_toast () {
+       if (deleted_alarm == null) {
+           return;
+       }
+
+       // only one toast at a time
+       if (ring_time_toast != null) {
+           ring_time_toast.dismiss ();
+       }
+
+       var window = (Clocks.Window) get_root ();
+       delete_toast = new Adw.Toast ("");
+
+       delete_toast.set_title (_("Alarm deleted"));
+       delete_toast.set_button_label (_("Undo"));
+       delete_toast.button_clicked.connect (() => {
+           if (deleted_alarm != null) {
+               alarms.add (deleted_alarm);   // ↩️ restore
+               connect_item (deleted_alarm); // re-hook signals/UI
+               deleted_alarm = null;
+               save ();
+               delete_toast.dismiss ();
+           }
+       });
+
+       delete_toast.dismissed.connect (() => {
+           deleted_alarm = null;  // GC once toast times out
+       });
+
+       window.add_toast (delete_toast);
+   }
```
</details> 
