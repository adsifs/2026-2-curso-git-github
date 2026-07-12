# Exercício 01 — Primeiro Repositório Local

> 📚 Fazer após o [Módulo 3](../03-comandos-basicos/README.md)
> 🎯 Objetivo: dominar o ciclo `init` → editar → `add` → `commit` → `log`

## Enunciado

1. Crie uma pasta chamada `meu-primeiro-repo` e transforme-a em um repositório Git;

2. Crie um arquivo `sobre-mim.md` com o seguinte conteúdo (adaptado para você):

   ```markdown
   # Sobre mim

   - **Nome:** Seu Nome
   - **Curso:** Seu Curso
   - **Semestre:** 2º
   ```

3. Faça o **primeiro commit** com a mensagem `"Adiciona apresentação inicial"`;

4. Edite o arquivo adicionando uma nova seção:

   ```markdown
   ## Linguagem que quero aprender

   Escreva aqui 1 ou 2 frases.
   ```

5. Antes de commitar, use `git diff` para conferir a mudança e `git status` para ver o estado do arquivo;

6. Faça o **segundo commit** com uma mensagem adequada (você decide — aplique o que viu no material);

7. Crie um segundo arquivo, `metas.md`, com 3 metas suas para o semestre, e commite-o (**terceiro commit**);

8. Exiba o histórico com `git log --oneline` e confira: devem aparecer **3 commits**.

## Desafio extra 🌶️

- Edite o `metas.md`, arrependa-se da edição e desfaça-a com `git restore` **antes** de fazer `add`;
- Confirme com `git status` e `git diff` que o arquivo voltou ao estado do último commit.

## ✅ Critérios de conclusão

- [ ] Repositório criado com `git init`;
- [ ] Exatamente 3 commits no `git log`;
- [ ] Mensagens de commit descritivas (nada de "commit 2");
- [ ] Você sabe explicar o que cada comando fez.

> 💾 **Guarde este repositório!** Ele será usado no Exercício 02.
