# Módulo 6 — Fluxo de Trabalho e Colaboração

> ⏱️ Duração estimada: 45 minutos
> 📋 Pré-requisitos: [Módulo 5](../05-branches/README.md)

Este módulo apresenta os recursos de **colaboração** do GitHub: como contribuir com repositórios de outras pessoas e como equipes trabalham juntas. É assim que funciona o open source — e a maioria das empresas.

## 6.1 Issues — o mural de tarefas e dúvidas

Uma **Issue** é um registro público de qualquer coisa relacionada ao projeto: bug encontrado, sugestão de melhoria, dúvida, tarefa a fazer.

Para criar: aba **Issues** → **New issue** → título claro + descrição detalhada → **Submit**.

Boas práticas ao abrir uma issue:

- ✅ **Título específico:** "Erro de digitação no Módulo 3, seção 3.5" (e não "achei um erro");
- ✅ **Descreva o contexto:** o que você esperava, o que aconteceu, como reproduzir;
- ✅ Use **Markdown**: blocos de código com ```` ``` ````, listas, prints;
- 💬 Nas issues também é possível conversar: cada issue tem uma thread de comentários.

> 🎓 **Nesta disciplina:** dúvidas sobre o material podem ser abertas como issues **neste repositório**. Assim, a resposta fica pública e ajuda toda a turma.

## 6.2 Os dois cenários de colaboração

| Cenário | Quando | Mecanismo |
|---------|--------|-----------|
| **Colaborador** | Você **tem permissão** de escrita no repositório (ex.: trabalho em grupo, repo da equipe) | Clona, cria branch, push, Pull Request |
| **Contribuidor externo** | Você **não tem permissão** (ex.: projeto open source, repositório do professor) | **Fork** primeiro, depois o mesmo fluxo |

## 6.3 Fork — sua cópia de um repositório alheio

Um **fork** é uma cópia completa de um repositório de outra pessoa **para a sua conta**. Nela você tem controle total — pode commitar e fazer push à vontade sem afetar o original.

Para criar: na página do repositório, botão **Fork** (canto superior direito) → **Create fork**.

Resultado: `github.com/professor/projeto` → **`github.com/VOCE/projeto`** (seu fork).

```
   REPOSITÓRIO ORIGINAL                     SEU FORK                       SUA MÁQUINA
  github.com/professor/projeto    fork    github.com/voce/projeto   clone   pasta local
  ┌──────────────────────┐   ─────────▶  ┌─────────────────────┐  ──────▶  ┌───────────┐
  │  (sem permissão       │              │  (controle total)     │          │           │
  │   de escrita)         │  ◀─────────  │                      │  ◀──────  │           │
  └──────────────────────┘ Pull Request └─────────────────────┘   push     └───────────┘
```

## 6.4 Pull Request — propondo suas mudanças

Um **Pull Request (PR)** é um pedido formal: *"analisem minhas mudanças e, se estiverem boas, incorporem ao projeto"*. É o coração da colaboração no GitHub — todo código em equipe passa por PRs, que permitem **revisão e discussão antes** de o código entrar no branch principal.

### O fluxo completo (contribuidor externo)

```bash
# 1. Fork pelo site (botão Fork)

# 2. Clone o SEU fork
git clone https://github.com/VOCE/projeto.git
cd projeto

# 3. Crie um branch descritivo para sua contribuição
git switch -c corrige-typo-modulo3

# 4. Faça as mudanças e commite
git add .
git commit -m "Corrige erro de digitação no módulo 3"

# 5. Envie o branch para o SEU fork
git push -u origin corrige-typo-modulo3
```

6. No GitHub, o site detecta o push e mostra um botão amarelo **"Compare & pull request"** — clique nele;
7. Escreva um **título** e uma **descrição** explicando *o que* mudou e *por quê*;
8. **Create pull request**. ✅

A partir daí, o dono do projeto pode:

- 💬 **Comentar** e pedir ajustes (você faz novos commits no mesmo branch — o PR atualiza sozinho);
- ✅ **Aprovar e fazer merge** — suas mudanças entram no projeto original;
- ❌ **Fechar** sem merge, explicando o motivo.

> 💡 **Por que "pull request"?** Você está *pedindo* (*request*) que o mantenedor *puxe* (*pull*) suas mudanças para o projeto dele.

### O fluxo em equipe (com permissão de escrita)

Igual, mas sem fork: todos clonam o **mesmo** repositório, cada um trabalha em **seu branch**, e os PRs são abertos entre branches do próprio repositório (`meu-branch` → `main`).

> 📏 **Regra de equipe:** nunca commitar direto no `main`. Todo mundo trabalha em branch + PR. Assim o `main` está sempre funcionando e todo código é revisado por pelo menos um colega.

## 6.5 Markdown — a língua franca do GitHub

READMEs, issues, PRs e comentários usam **Markdown**. O essencial:

```markdown
# Título 1
## Título 2

**negrito**  *itálico*  `código inline`

- item de lista
- outro item

1. lista numerada
2. segundo item

[texto do link](https://exemplo.com)
![descrição da imagem](caminho/imagem.png)

​```javascript
// bloco de código com syntax highlighting
console.log("olá");
​```

| Coluna A | Coluna B |
|----------|----------|
| valor    | valor    |

- [ ] checkbox pendente
- [x] checkbox concluído
```

> 💡 Este material inteiro foi escrito em Markdown. Clique em **Raw** em qualquer página para ver o código-fonte — é um ótimo jeito de aprender.

## ✅ Checkpoint do módulo

1. Quando é necessário fazer fork antes de contribuir?
2. Qual a sequência completa: fork → ? → ? → ? → PR?
3. Por que equipes usam PRs em vez de commitar direto no `main`?
4. Para que servem as Issues?

🏋️ **Agora faça o [Exercício 04](../exercicios/exercicio-04.md)!**

---

⬅️ [Módulo 5 — Branches](../05-branches/README.md) | ➡️ [Módulo 7 — Boas Práticas](../07-boas-praticas/README.md)
