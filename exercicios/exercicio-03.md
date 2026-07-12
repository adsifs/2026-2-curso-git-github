# Exercício 03 — Branches e Merge

> 📚 Fazer após o [Módulo 5](../05-branches/README.md)
> 🎯 Objetivo: criar branches, mesclar e resolver um conflito de verdade

## Parte A — Merge tranquilo (sem conflito)

1. No repositório `meu-primeiro-repo`, crie um branch chamado `hobbies` e mude para ele;

2. Nesse branch, crie um arquivo novo `hobbies.md` listando 3 hobbies seus, e commite;

3. Volte ao `main` e confirme que o arquivo `hobbies.md` **não aparece** na pasta (use `ls`);

4. Faça o merge do branch `hobbies` no `main` e confirme que o arquivo agora existe;

5. Apague o branch `hobbies` (`git branch -d hobbies`).

## Parte B — Provocando e resolvendo um conflito

6. Crie um branch `titulo-novo`. Nele, altere a **primeira linha** do `sobre-mim.md` para:

   ```markdown
   # Quem sou eu
   ```

   Commite a mudança;

7. Volte ao `main` e altere **a mesma primeira linha** para:

   ```markdown
   # Apresentação
   ```

   Commite;

8. Tente fazer o merge de `titulo-novo` no `main` — o Git vai acusar **CONFLICT**;

9. Abra o arquivo, observe as marcações `<<<<<<<`, `=======`, `>>>>>>>` e resolva o conflito escolhendo o título que preferir (ou um terceiro);

10. Conclua o merge (`git add` + `git commit`) e visualize o resultado com:

    ```bash
    git log --oneline --graph
    ```

11. Envie tudo para o GitHub com `git push`.

## Desafio extra 🌶️

- Crie um branch, faça um commit nele e envie **o branch** para o GitHub (`git push -u origin nome-do-branch`);
- No site, use o seletor de branches para navegar entre `main` e o novo branch e observe a diferença nos arquivos.

## ✅ Critérios de conclusão

- [ ] Você fez um merge sem conflito (Parte A) e um com conflito (Parte B);
- [ ] O conflito foi resolvido e não sobraram marcações `<<<<<<<` no arquivo;
- [ ] O `git log --oneline --graph` mostra o histórico com a bifurcação;
- [ ] Tudo enviado ao GitHub.
