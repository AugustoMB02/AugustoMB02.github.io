---
layout: post
title: Contributing to a Debian Package — First Steps
subtitle: A running log for “MAC0470 – Desenvolvimento de Software Livre”
tags: [mac0470, usp, floss, software, debian, packaging]
author: Augusto Mariano Bernardi
---

### Weekly Progress Log

#### Parte 1 — Configurando o Ambiente
Segui o tutorial da comunidade **Debian Brasil** para preparar meu ambiente de empacotamento:  
<https://debianbrasil.org.br/empacotamento/configurando-seu-ambiente>  
Tudo ocorreu quase sem problemas: instalei `devscripts`, `lintian`, configurei minha chave GPG e criei a conta no Salsa.
O uníco problema foi ao editar o arquivo "~/.bashrc" pois ouve um typo ao digitar o email e tive que gastar cerca de 10 minutos até notar que esse foi o problema ao testar a configuração.

#### Parte 2 — A contribuição
A contribuição foi realizada em aula, graças aos palestrantes Charles e Lucas Kanashiro o processo foi relativamente fácil e ajudou a compreender como funciona a contribuição.
Primeiro selecionamos de uma lista de pacotes curados pelos palestrantes, e então abrimos uma issue <https://salsa.debian.org/debian-brasil-team/docs/-/issues/506> e a contribuição consistiu em atualizar a standard version que o pacote é compliant.


---

### Reference Checklist (fill in as you go)

- [ ] Added myself to `debian/changelog`
- [ ] Bumped `Standards-Version`
- [ ] Cleared all Lintian warnings
- [ ] Verified reproducible build
- [ ] Signed commits & uploaded source
- [ ] Opened Merge Request / sent debdiff
- [ ] Responded to reviewer comments

---

### Resources & Links
* Debian New Maintainer’s Guide, Policy Manual, `#debian-mentors` IRC, Salsa project home, BTS ticket URL, etc.*

---
