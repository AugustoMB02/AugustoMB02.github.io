---
layout: post
title: Final Reflections on “MAC0470 – Desenvolvimento de Software Livre”
subtitle: From kernel headaches to FLOSS enlightenment
tags: [mac0470, usp, floss, reflections, software]
author: Augusto Mariano Bernardi
---

## 1 · Revisitando as Duas Metades do Curso

### 1.1 Kernel Hacking — Quando a teoria encontra a dureza do hardware
* **Ambiente hostil** — VMs que perdiam IP, consoles congelados e imagens corrompidas tornaram cada *make menuconfig* uma aventura.
* **Contribuição frustrada** — Mesmo após entender o fluxo de _patch_ (e até esboçar correções), passava mais tempo depurando a infraestrutura do que escrevendo código para o kernel.
* **Lição aprendida** — *Development workflow* inclui garantir **infra** confiável; sem ela, o melhor patch nunca nasce.

### 1.2 Empacotamento Debian — O ponto de virada
* **Ferramentas bem-calibradas** (`devscripts`, `lintian`, GPG, Salsa) → produtividade imediata.
* **Processo guiado** — Issues curadas + mentoria de Charles & Lucas Kanashiro transformaram a contribuição em algo tangível.
* **Primeiro MR** — Atualizar `Standards-Version` e assinar o `debian/changelog` parece simples, mas mostrou o rigor que mantém o ecossistema Debian saudável.

## 2 · FLOSS além do Código-fonte

| Eixo | O que mudou na minha visão |
|------|---------------------------|
| **Licenças** | De “texto jurídico chato” para **garantia prática de liberdade**. |
| **Governança** | A ausência de CNPJ no Debian evita amarras políticas: qualquer pessoa, em qualquer país, pode usar e redistribuir. |
| **Comunidade** | FLOSS é **infraestrutura social**: mailing lists, IRC e hackerspaces são tão críticos quanto o Git. |

> **Insight central:** contribuir não é apenas “adicionar linhas de código”, mas **sustentar um ecossistema inclusivo** onde conhecimento e software permanecem livres de barreiras corporativas ou geopolíticas.

## 3 · Aprendizados Técnicos Essenciais

1. **Controle de versões disciplinado** — _Commits_ atômicos, assinar tags, usar _branches_ de integração.  
2. **Automação de QA** — `lintian`, `autopkgtest`, builds reprodutíveis.  
3. **Cultura de revisão** — Feedback rápido, respeito ao _guideline_ do mantenedor e comunicação assíncrona clara.  

## 4 · Desafios que Permanecem

* **Infraestrutura pessoal** — Montar um laboratório local robusto (em vez de depender de VMs frágeis).
* **Profundidade no Kernel** — Voltar ao patch abandonado com um ambiente estável e, enfim, submetê-lo.
* **Manutenção contínua** — Adotar um *orphaned package* para vivenciar o ciclo completo de versões.

## 5 · Próximos Passos

* **Participar do `#debian-mentors`** semanalmente.  
* **Contribuir na tradução de manuais do Debian Brasil**.  
* **Organizar um _mini-sprint_ de empacotamento na Poli/USP** — multiplicar o aprendizado.

---

### 6 · Agradecimentos

> Aos palestrantes, TAs e colegas que mantiveram o bom humor enquanto eu lutava com _kernels_ rebeldes. Sem a paciência de vocês, esse post teria apenas linhas de stack-trace.

**Spoiler pessoal:** depois de tudo, considero inevitável continuar envolvido com FLOSS — afinal, agora soa menos como trabalho e mais como **cidadania digital**.

---
