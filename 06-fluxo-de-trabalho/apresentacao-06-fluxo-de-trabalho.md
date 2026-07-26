---
marp: true
theme: trilha
paginate: true
lang: pt-BR
footer: '📚 Curso de Git e GitHub · Módulo 6'
---

<!-- _class: capa -->

<div class="emoji">🤝</div>

# Fluxo de Trabalho e Colaboração

## Módulo 6 · Curso de Git e GitHub

<div class="meta">⏱️ 45 minutos &nbsp;·&nbsp; 📋 Requer o Módulo 5</div>

---

## Roteiro

Até aqui você trabalhou sozinho. Agora entram os recursos de **colaboração** do GitHub.

1. **Issues** — o mural do projeto
2. Os dois cenários de colaboração
3. **Fork** — sua cópia de um repositório alheio
4. **Pull Request** — propondo suas mudanças
5. **Markdown** — a língua franca do GitHub

> 💡 É exatamente assim que funciona o open source — e a maioria das empresas.

---

## Issues — o mural do projeto

Uma **Issue** é um registro público de qualquer coisa ligada ao projeto: um bug encontrado, uma sugestão, uma dúvida, uma tarefa a fazer.

**Aba Issues → New issue → título + descrição → Submit.**

> 💡 Cada issue tem uma **thread de comentários** — dá para conversar ali, e a conversa fica registrada para quem chegar depois.

---

<!-- _class: lista-limpa -->

## Como abrir uma issue que ajuda

- ✅ **Título específico:** *"Erro de digitação no Módulo 3, seção 3.5"* — e não *"achei um erro"*;
- ✅ **Contexto:** o que você esperava, o que aconteceu, como reproduzir;
- ✅ **Markdown:** blocos de código, listas, prints;
- ❌ Evite issues que só dizem *"não funciona"* — ninguém consegue agir a partir disso.

---

## Os dois cenários de colaboração

| Cenário | Quando | Mecanismo |
|---|---|---|
| **Colaborador** | você **tem** permissão de escrita — repo da equipe | clone → branch → push → PR |
| **Contribuidor externo** | você **não tem** permissão — projeto open source | **fork** primeiro, depois o mesmo fluxo |

---

## Fork — sua cópia de um repositório alheio

Uma cópia completa do repositório de outra pessoa, **para a sua conta**. Nela você tem controle total: commita e dá push à vontade, sem afetar o original.

Botão **Fork** (canto superior direito) → **Create fork**.

```
github.com/outra-pessoa/projeto   →   github.com/VOCE/projeto
```

---

<!-- _class: diagrama -->

## Do fork ao Pull Request

![w:1140](img/fork-e-pull-request.svg)

---

## Pull Request — o pedido formal

> *"Analisem minhas mudanças e, se estiverem boas, incorporem ao projeto."*

É o coração da colaboração no GitHub: todo código feito em equipe passa por PR, porque o PR permite **revisão e discussão antes** de o código entrar no branch principal.

---

<!-- _class: lead -->

## 💡 Por que "pull request"?

Você está **pedindo** (*request*)
que o mantenedor **puxe** (*pull*)
as suas mudanças para o projeto dele.

O trabalho é seu; a decisão de aceitar é dele.

---

## O fluxo, passos 1 a 5 — no terminal

```bash
# 1. Fork pelo site (botão Fork)
# 2. Clone o SEU fork — não o original
git clone https://github.com/VOCE/projeto.git
cd projeto
# 3. Um branch descritivo para a contribuição
git switch -c corrige-typo-modulo3
# 4. Faça as mudanças e commite
git add . && git commit -m "Corrige erro de digitação"
# 5. Envie o branch para o SEU fork
git push -u origin corrige-typo-modulo3
```

---

## O fluxo, passos 6 a 8 — no site

**6.** O GitHub detecta o push e mostra o botão amarelo **"Compare & pull request"** — clique nele;

**7.** Escreva **título** e **descrição**, explicando *o que* mudou e *por quê*;

**8.** **Create pull request** ✅

> 💡 Se o mantenedor pedir ajustes, basta commitar de novo **no mesmo branch**: o PR se atualiza sozinho.

---

<!-- _class: lista-limpa -->

## O que o mantenedor faz com o seu PR

- 💬 **Comenta e pede ajustes** — você complementa no mesmo branch;
- ✅ **Aprova e faz merge** — suas mudanças entram no projeto original;
- ❌ **Fecha sem merge**, explicando o motivo.

---

## Em equipe: igual, sem o fork

Todos clonam o **mesmo** repositório. Cada um trabalha em **seu branch**, e os PRs são abertos entre branches do próprio repositório:

```
meu-branch  →  main
```

---

<!-- _class: lead -->

## 📏 Regra de equipe

**Nunca commitar direto no `main`.**

Todo mundo trabalha em branch e abre PR.

Assim o `main` está sempre funcionando, e todo código passou pelos olhos de pelo menos mais uma pessoa.

---

<!-- _class: tabela-densa -->

## Markdown — a língua franca do GitHub

READMEs, issues, PRs e comentários usam Markdown. O essencial:

| Você escreve | Vira |
|---|---|
| `# Título` &nbsp; `## Subtítulo` | títulos, do maior ao menor |
| `**negrito**` &nbsp; `*itálico*` | **negrito** e *itálico* |
| `` `código` `` | `código` destacado |
| `- item` &nbsp; `1. item` | listas, com e sem número |
| `[texto](url)` | link clicável |
| ` ```js ` … ` ``` ` | bloco de código colorido |
| `- [ ]` &nbsp; `- [x]` | caixas de tarefa |

---

## E o melhor jeito de aprender Markdown

> 💡 **Este material inteiro foi escrito em Markdown.**
>
> Em qualquer página do GitHub, clique em **Raw** para ver o código-fonte por trás do que está renderizado.

Abra o README de um módulo, veja o Raw, compare com o resultado. Em dez minutos você aprende mais do que em qualquer tutorial.

---

<!-- _class: checkpoint -->

## ✅ Checkpoint do módulo

1. Quando é necessário fazer fork antes de contribuir?
2. Qual a sequência completa: fork → ? → ? → ? → PR?
3. Por que equipes usam PR em vez de commitar direto no `main`?
4. Para que servem as Issues?

---

<!-- _class: lead -->

## 🏋️ Agora é com você

**Exercício 04 — Colaboração com Pull Request**

`exercicios/exercicio-04.md`

Depois, o **Módulo 7** fecha o curso com as
**boas práticas** que separam um repositório bom de um bagunçado.
