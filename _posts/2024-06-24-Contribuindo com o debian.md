---
layout: post
title: Contributing to a Debian Package — First Steps
subtitle: A running log for “MAC0470 – Desenvolvimento de Software Livre”
tags: [mac0470, usp, floss, software, debian, packaging]
author: Augusto Mariano Bernardi
---

### Progress Log

#### Parte 1 — Configurando o Ambiente
Segui o tutorial da comunidade **Debian Brasil** (<https://debianbrasil.org.br/empacotamento/configurando-seu-ambiente>) para preparar meu ambiente de empacotamento.  
Instalei as dependencias, configurei o ambiente e criei a conta no Salsa quase sem tropeços. O único contratempo foi um **typo** no endereço de e-mail dentro do `~/.bashrc`; perdi cerca de dez minutos até descobrir que ele era o responsável pelos erros durante os testes de assinatura.

#### Parte 2 — A Contribuição
A contribuição prática aconteceu em aula e foi facilitada pelos palestrantes **Charles** e **Lucas Kanashiro**. O fluxo, em resumo, foi:

1. **Escolha do pacote** — trabalhamos com uma lista “curada” de pacotes mantidos pela comunidade.  
2. **Registro da tarefa** — abrimos a *issue* <https://salsa.debian.org/debian-brasil-team/docs/-/issues/506> para acompanhar o trabalho.  
3. **Atualização de `Standards-Version`** — ajustamos o campo no `debian/control` para a versão de política atual.  
4. **Entrada no `debian/changelog`** — descrevi a alteração e assinei o *commit*.

Graças ao roteiro fornecido e às explicações sobre boas práticas de *git* para Debian, o processo foi direto e muito didático.

---

### Considerações Finais
Embora colocar a mão na massa e subir um *merge request* já tenha sido enriquecedor, **o ponto alto da atividade foram as palestras**. Nelas ficou claro:

* **Filosofia Debian** — software deve permanecer livre de verdade, sem barreiras corporativas ou políticas.  
* **Ausência de CNPJ** — Debian não é uma empresa; isso evita amarras legais que poderiam limitar a distribuição em certos países.  
* **Neutralidade em relação a governos** — qualquer pessoa, em qualquer jurisdição, pode usar e redistribuir Debian sem depender de licenças sujeitas a embargos (por exemplo, restrições dos EUA).

Essa perspectiva ampliou minha visão sobre o que significa contribuir para o FLOSS: não é só “mandar patches”, mas sustentar um ecossistema aberto onde todos — independente de fronteiras — têm direito de criar, aprender e compartilhar.

> **Próximos passos:** continuar acompanhando as listas de discussão, escolher um pacote que uso no dia a dia e, quem sabe, adotar um *orphaned package* para manter de forma contínua.

---

