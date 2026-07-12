# Exercício 04 — Colaboração com Pull Request

> 📚 Fazer após o [Módulo 6](../06-fluxo-de-trabalho/README.md)
> 🎯 Objetivo: executar o fluxo completo fork → branch → commit → push → Pull Request
> 👥 Este exercício usa um **repositório da turma** indicado pelo professor

## Cenário

O professor criou um repositório chamado **`mural-da-turma`** (o link será passado em aula). Ele contém uma pasta `alunos/`, e cada aluno deve adicionar seu próprio arquivo de apresentação **via Pull Request** — exatamente como se contribui com um projeto open source.

## Enunciado

1. Acesse o repositório `mural-da-turma` e faça um **Fork** para a sua conta;

2. **Clone o seu fork** (atenção: o seu, não o original!) para sua máquina;

3. Crie um branch com seu nome, por exemplo:

   ```bash
   git switch -c adiciona-maria-silva
   ```

4. Dentro da pasta `alunos/`, crie o arquivo `seu-nome.md` (ex.: `maria-silva.md`) seguindo o modelo:

   ```markdown
   # Maria Silva

   - **GitHub:** [maria-silva](https://github.com/maria-silva)
   - **Uma curiosidade sobre mim:** ...
   - **O que espero aprender neste semestre:** ...
   ```

5. Commite com uma mensagem adequada e envie o branch para o **seu fork**;

6. No GitHub, abra o **Pull Request** do seu branch para o `main` do repositório **original**:
   - Título: `Adiciona apresentação de Maria Silva`;
   - Descrição: uma frase sobre o que o PR faz;

7. Acompanhe o PR: se o professor comentar pedindo ajuste, faça a correção **no mesmo branch**, commite e dê push — o PR se atualiza sozinho;

8. Depois que o PR for aceito (merge), visite o repositório original e encontre seu arquivo lá. 🎉

## Desafio extra 🌶️

- Abra uma **Issue** no repositório do curso relatando algo que você achou confuso no material ou sugerindo uma melhoria — capriche no título e na descrição;
- Revise o PR de um colega: abra o PR dele, vá em **Files changed** e deixe um comentário construtivo.

## ✅ Critérios de conclusão

- [ ] Fork criado na sua conta;
- [ ] PR aberto a partir de um branch (não do `main`);
- [ ] Arquivo segue o modelo e está na pasta correta;
- [ ] PR aceito e mudança visível no repositório original.
