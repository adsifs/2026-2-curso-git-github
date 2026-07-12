# ⚡ Cheatsheet — Git e GitHub

> A "cola" oficial do semestre. Marque esta página nos favoritos!

## 🔄 O ciclo do dia a dia (90% do que você precisa)

```bash
git pull                       # 1. SEMPRE comece atualizando
# ... trabalhe nos arquivos ...
git status                     # 2. veja o que mudou
git add .                      # 3. prepare as mudanças
git commit -m "Mensagem clara" # 4. fotografe
git push                       # 5. SEMPRE termine enviando
```

## ⚙️ Configuração (uma vez só)

| Comando | O que faz |
|---------|-----------|
| `git config --global user.name "Nome"` | Define seu nome nos commits |
| `git config --global user.email "email"` | Define seu e-mail (o mesmo do GitHub!) |
| `git config --list` | Mostra as configurações |

## 📁 Criando/obtendo repositórios

| Comando | O que faz |
|---------|-----------|
| `git init` | Transforma a pasta atual em repositório |
| `git clone <url>` | Baixa um repositório completo do GitHub |

## 📸 Ciclo básico

| Comando | O que faz |
|---------|-----------|
| `git status` | Situação atual (use o tempo todo!) |
| `git add <arquivo>` | Envia o arquivo para o stage |
| `git add .` | Envia tudo que mudou para o stage |
| `git commit -m "msg"` | Grava a foto no histórico |
| `git diff` | Mudanças ainda não staged |
| `git diff --staged` | Mudanças já staged |
| `git log` | Histórico completo |
| `git log --oneline` | Histórico resumido (1 linha por commit) |
| `git log --oneline --graph` | Histórico com desenho dos branches |

## ☁️ Sincronização com o GitHub

| Comando | O que faz |
|---------|-----------|
| `git remote add origin <url>` | Conecta o repo local ao GitHub (1ª vez) |
| `git remote -v` | Mostra os remotos configurados |
| `git push -u origin main` | Primeiro envio (cria o vínculo) |
| `git push` | Envia commits (após o 1º push) |
| `git pull` | Baixa e aplica commits do remoto |

## 🌿 Branches

| Comando | O que faz |
|---------|-----------|
| `git branch` | Lista os branches (`*` = atual) |
| `git switch -c <nome>` | Cria um branch e muda para ele |
| `git switch <nome>` | Muda para um branch existente |
| `git merge <nome>` | Mescla `<nome>` no branch atual |
| `git branch -d <nome>` | Apaga um branch (já mesclado) |
| `git push -u origin <nome>` | Envia um branch ao GitHub |

## ↩️ Desfazendo (com cuidado!)

| Situação | Comando |
|----------|---------|
| Descartar edição não commitada ⚠️ | `git restore <arquivo>` |
| Tirar arquivo do stage | `git restore --staged <arquivo>` |
| Corrigir a mensagem do último commit | `git commit --amend -m "Nova msg"` |
| Parar de rastrear arquivo já commitado | `git rm --cached <arquivo>` |

## 🧯 Emergências comuns

| Sintoma | Causa provável | Solução |
|---------|----------------|---------|
| `rejected... fetch first` no push | O remoto tem commits que você não tem | `git pull` e depois `git push` |
| `CONFLICT` no merge/pull | Mesma linha alterada em dois lugares | Edite o arquivo, remova `<<<<<<<`/`=======`/`>>>>>>>`, `add` + `commit` |
| `Authentication failed` | Senha em vez de token | Use o **token** como senha |
| `not a git repository` | Você não está na pasta do repo | `cd` até a pasta certa (confira com `pwd`/`ls`) |
| Commitei `node_modules` 😱 | Faltou `.gitignore` | Crie o `.gitignore`, depois `git rm -r --cached node_modules/` + commit |

Mais casos no [guia de solução de problemas](recursos/solucao-de-problemas.md).

## 🧠 Vocabulário em 10 segundos

**repo** = projeto + histórico · **commit** = foto do projeto · **stage** = fila para a próxima foto · **branch** = linha paralela de trabalho · **merge** = juntar branches · **origin** = apelido do remoto no GitHub · **push** = subir · **pull** = baixar · **clone** = baixar repo inteiro (1ª vez) · **fork** = cópia de repo alheio para sua conta · **PR** = pedido para incorporarem suas mudanças

---

🏠 [Voltar ao início](README.md)
