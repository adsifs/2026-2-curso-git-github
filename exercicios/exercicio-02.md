# Exercício 02 — Publicando no GitHub

> 📚 Fazer após o [Módulo 4](../04-github/README.md)
> 🎯 Objetivo: conectar um repositório local ao GitHub e dominar `push` e `pull`
> 📋 Pré-requisito: [Exercício 01](exercicio-01.md) concluído

## Enunciado

1. Crie no GitHub um repositório **vazio** (sem README) chamado `meu-primeiro-repo`;

2. Conecte o repositório local do Exercício 01 a ele (`git remote add origin ...`);

3. Envie os commits com `git push -u origin main` e **confira no navegador** que os 3 commits e os 2 arquivos estão lá;

4. **Pela interface do GitHub**, edite o arquivo `sobre-mim.md`: adicione uma linha qualquer e commite pelo próprio site;

5. No terminal, traga essa mudança para sua máquina com `git pull`;

6. Localmente, adicione ao `metas.md` uma quarta meta, commite e envie com `git push`;

7. No GitHub, abra a aba de **commits** do repositório e observe o histórico completo: deve haver commits feitos localmente **e** pelo site.

## Desafio extra 🌶️

- Em **outra pasta** da sua máquina (simulando "o computador da faculdade"), clone o mesmo repositório com `git clone`;
- Nessa cópia, faça uma alteração, commite e dê push;
- Volte à pasta original e atualize-a com `git pull`. Você acabou de simular o fluxo de quem trabalha em duas máquinas!

## ✅ Critérios de conclusão

- [ ] Repositório visível no seu perfil do GitHub;
- [ ] Histórico contém commits locais e um commit feito pela interface web;
- [ ] Você executou `push` e `pull` pelo menos uma vez cada e sabe explicar a diferença;
- [ ] O repositório local e o remoto estão sincronizados (`git status` mostra *"up to date with 'origin/main'"*).
