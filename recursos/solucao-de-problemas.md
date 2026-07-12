# 🧯 Socorro! Deu Erro!

Guia dos erros mais comuns do semestre, com causa e solução. Antes de pedir ajuda, procure aqui — e leia a mensagem de erro: **o Git quase sempre diz o que fazer** na própria mensagem.

## Erros de configuração e autenticação

### `Please tell me who you are`

```
*** Please tell me who you are.
Run
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```

**Causa:** você tentou commitar sem configurar nome/e-mail.
**Solução:** rode exatamente os dois comandos que a mensagem mostra (com os **seus** dados) e commite de novo.

### `Authentication failed` / `Support for password authentication was removed`

**Causa:** você digitou a **senha da conta** do GitHub em vez do **token**.
**Solução:** use o token (Módulo 2) no campo de senha. Perdeu o token? Gere outro — Settings → Developer settings → Personal access tokens.

### `Permission denied to <usuario>` (403)

**Causa:** você está tentando dar push num repositório que **não é seu** (ex.: clonou o repo do professor em vez de fazer fork).
**Solução:** faça um **fork**, clone **o seu fork** e trabalhe nele (Módulo 6). Ou, se o repo é seu, verifique se o token guardado é da conta certa.

## Erros de "onde estou?"

### `fatal: not a git repository`

**Causa:** você está numa pasta que não é um repositório.
**Solução:** use `pwd` e `ls` para se localizar e `cd` até a pasta do projeto. Se a pasta realmente ainda não é um repo, rode `git init` (só se for a raiz do seu projeto!).

### Rodei `git init` na pasta errada (ex.: Documentos inteira) 😱

**Solução:** apague apenas a pasta oculta `.git` de lá:

```bash
cd pasta-errada
rm -rf .git
```

Isso remove o repositório **sem tocar nos seus arquivos**.

## Erros de push/pull

### `! [rejected] main -> main (fetch first)`

```
error: failed to push some refs to '...'
hint: Updates were rejected because the remote contains work that you do not have locally.
```

**Causa:** o remoto tem commits que sua máquina não tem (você editou pelo site, ou trabalhou em outro PC, ou um colega enviou algo).
**Solução:**

```bash
git pull      # traz os commits do remoto (pode gerar conflito — resolva se preciso)
git push      # agora vai
```

### `There is no tracking information for the current branch`

**Causa:** primeiro push de um branch sem o `-u`.
**Solução:** `git push -u origin nome-do-branch` (só na primeira vez).

### Fiz push mas o professor diz que não vê nada

**Checklist:**
1. O `git push` realmente terminou sem erro?
2. Você commitou antes do push? (`git log` mostra o commit?)
3. Está olhando o repositório certo? Abra a URL **no navegador** e confira;
4. O branch certo? Se commitou num branch, o `main` do site não mostra.

## Conflitos

### `CONFLICT (content): Merge conflict in <arquivo>`

**Não entre em pânico.** É normal e tem solução em 3 passos:

1. Abra o arquivo indicado e localize as marcações:

   ```
   <<<<<<< HEAD
   (sua versão)
   =======
   (a outra versão)
   >>>>>>> nome-do-branch
   ```

2. Edite deixando só o conteúdo final desejado, **apagando as três linhas de marcação**;
3. `git add <arquivo>` e `git commit` (pode deixar a mensagem padrão do merge).

Quer desistir do merge e voltar como estava? `git merge --abort`.

## Arquivos indesejados

### Commitei `node_modules/` (ou `.class`, `target/`...)

**Solução:**

```bash
# 1. Garanta que o padrão está no .gitignore
echo "node_modules/" >> .gitignore

# 2. Remova do rastreamento (os arquivos continuam no disco)
git rm -r --cached node_modules/

# 3. Commite a limpeza
git add .gitignore
git commit -m "Remove node_modules do versionamento"
git push
```

### Commitei uma senha/token 🔥

**Considere o segredo vazado** — remover o arquivo em um commit novo **não apaga o histórico**.

1. **Revogue/troque o segredo imediatamente** (gere novo token, troque a senha);
2. Remova o arquivo do repositório e adicione ao `.gitignore`;
3. Avise o professor. (Limpar o histórico é possível, mas é assunto avançado — o passo 1 é o que importa.)

## Editor estranho abriu no terminal

### Tela cheia de `~` e você não consegue sair (Vim)

**Causa:** `git commit` sem `-m` (ou um merge) abriu o editor padrão, o Vim.
**Solução para sair:** pressione `Esc`, digite `:wq` e `Enter` (salva e sai). Para sair **sem** salvar: `Esc`, `:q!`, `Enter`.
**Prevenção:** use sempre `-m "mensagem"`, ou configure o VS Code como editor: `git config --global core.editor "code --wait"`.

## Regra de ouro do debugging

> 🔍 **Leia a mensagem de erro em voz alta.** O Git é verboso de propósito: na maioria das vezes a solução está escrita ali, nas linhas que começam com `hint:`. Cole a mensagem no Google se precisar — 100% dos erros que você terá já aconteceram com milhões de pessoas.

---

🏠 [Voltar ao início](../README.md) | ⚡ [Cheatsheet](../cheatsheet.md)
