---
layout: post
title: Final Reflections on “MAC0470 – Desenvolvimento de Software Livre”
subtitle: From kernel headaches to FLOSS enlightenment
tags: [mac0470, usp, floss, reflections, software]
author: Augusto Mariano Bernardi
---

## 1 · Revisitando o Curso

### 1.1 Kernel Hacking — Quando a teoria encontra a dureza do hardware
* **Ambiente hostil** — VMs que perdiam IP, consoles congelados e imagens corrompidas tornaram cada *make menuconfig* uma aventura/pesadelo.
* **Contribuição frustrada** — Mesmo após entender o fluxo de _patch_, passava mais tempo depurando a infraestrutura do que fazendo contribuições.
* **Resultado** — No fim não consegui fazer os tutoriais funcionarem na minha máquina, e minha contribuição ficou limitada a revisar brevemente o código de minha dupla.

### 1.2 Contribuição no GNOME — quando as coisas realmente começaram a fluir
* **Garimpando _issues_** — Passei um bom tempo vasculhando as _issues_ de diversos aplicativos do GNOME e foquei naqueles que uso no dia a dia; queria que a minha contribuição me beneficiasse diretamente. Acabei encontrando uma tarefa no **GNOME Clocks**: adicionar um botão **Undo** para alarmes deletados. Pareceu um desafio dentro da minha capacidade — mesmo sem experiência prévia em Vala — com uma funcionalidade de valor prático.  
* **Mãos à obra** — Depois de clonar e _forkar_ a versão mais recente no GitLab, configurei o ambiente e implementei o botão. A alteração no código foi relativamente direta e os testes locais passaram sem problemas.  
* **Status do _merge_** — Até a redação deste post, o _merge_ ainda não foi efetuado. Pelo histórico do projeto, os mantenedores costumam integrar contribuições pouco antes de um novo release, então sigo acompanhando a fila de revisões.

### 1.3 Empacotamento Debian — O ponto de virada
* **Ferramentas bem-calibradas** (`devscripts`, `lintian`, GPG, Salsa) → produtividade imediata.
* **Processo guiado** — Issues curadas + mentoria de Charles & Lucas Kanashiro transformaram a contribuição em algo tangível.
* **Primeiro MR** — Atualizar `Standards-Version` e assinar o `debian/changelog` parece simples, mas mostrou o rigor que mantém o ecossistema Debian saudável.

### 1.4 Segunda contribuição ao GNOME — Ausente
* **Razões pessoais** — Nas duas últimas semanas, adoeci por alguns dias e passei por outras circunstâncias pessoais que afetaram diretamente minha produtividade e motivação. Apesar disso, mantive algum contato com os projetos: voltei a explorar _issues_ no **Clocks**, além de dar uma olhada em problemas abertos no **Calendar**, **Boxes** e **Calculadora**. No entanto, não consegui avançar significativamente em nenhuma das tarefas que selecionei.

## 2 · FLOSS além do Código-fonte

| Eixo | O que mudou na minha visão |
|------|---------------------------|
| **Licenças** | De “texto jurídico chato” para **garantia prática de liberdade**. |
| **Governança** | Por exemplo, o Debian não ser uma empresa evita amarras políticas: qualquer pessoa, em qualquer país, pode usar e redistribuir. |
| **Comunidade** | FLOSS é **infraestrutura social**: mailing lists, IRC e hackerspaces são tão críticos quanto o Git. |

> **Insight central:** contribuir não é apenas “adicionar linhas de código”, mas **sustentar um ecossistema inclusivo** onde conhecimento e software permanecem livres de barreiras corporativas ou geopolíticas.

## 3 · Aprendizados Técnicos Essenciais

1. **Controle de versões disciplinado** — _Commits_ atômicos, assinar tags, usar _branches_ de integração.  
2. **Automação de QA** — `lintian`, `autopkgtest`, builds reprodutíveis.  
3. **Cultura de revisão** — Feedback rápido, respeito ao _guideline_ do mantenedor e comunicação assíncrona clara.  

## 4 · Desafios que Permanecem

* **Infraestrutura pessoal** — Montar um laboratório local robusto (em vez de depender de VMs frágeis).
* **Profundidade no Kernel** — Voltar ao passo um com um ambiente estável e, enfim, submetê-lo.
* **Manutenção contínua** — Adotar um *orphaned package* para vivenciar o ciclo completo de versões.

## 5 · Próximos Passos

* **Revisitar a tentativa de contribuição ao kernel** — Com um ambiente mais estável, tentar novamente aplicar um patch simples como forma de consolidar o aprendizado da primeira metade do curso.
* **Explorar novos projetos FLOSS** — Uso no meu dia a dia softwares da KDE, deveria realizar alguma contribuição.
* **Registrar tudo isso publicamente** — manter um blog ou repositório com as contribuições feitas, dificuldades encontradas e aprendizados, ajudando quem quiser seguir caminho parecido.


---

### 6 · Agradecimentos

> Aos palestrantes, TAs, professor e colegas que mantiveram o bom humor enquanto eu lutava com _kernels_ rebeldes. Sem a paciência de vocês, esse post talves nem existiria e teria trancado a matéria na quarta semana.

**Spoiler pessoal:** Eu usava Ubuntu no meu notebook antigo que carreguei pelo ensino médio, mas durante a pandemia voltei para o Windows, agora graças a disciplina instalei linux novamente e estou usando como meu sistema operacional principal novamente.

---
