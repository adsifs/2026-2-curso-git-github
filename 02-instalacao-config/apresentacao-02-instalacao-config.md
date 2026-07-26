---
marp: true
theme: trilha
paginate: true
lang: pt-BR
footer: '📚 Curso de Git e GitHub · Módulo 2'
---

<!-- _class: capa -->

<div class="emoji">🛠️</div>

# Instalação e Configuração

## Módulo 2 · Curso de Git e GitHub

<div class="meta">⏱️ 40 minutos &nbsp;·&nbsp; 📋 Requer o Módulo 1</div>

---

## Roteiro

1. **Instalar** o Git na sua máquina
2. **Configurar** a sua identidade
3. **Criar** a conta no GitHub
4. **Autenticar** a máquina no GitHub

> ⚠️ Este módulo é **para fazer junto**. Abra o terminal agora — no Windows, o **Git Bash**.

---

## 1️⃣ Instalar — Windows

1. Baixe em `git-scm.com/download/win`;
2. Execute o instalador;
3. **Aceite todas as opções padrão** — clique *Next* até o fim;
4. Ao terminar, você terá o **Git Bash**.

> 💡 No Windows, use **sempre o Git Bash** neste curso. Ele aceita os mesmos comandos do Linux e do macOS, então todo mundo vê a mesma tela.

---

## 1️⃣ Instalar — Linux e macOS

**Linux** (Ubuntu/Debian):

```bash
sudo apt update
sudo apt install git
```

**macOS** — com Homebrew, ou deixe o próprio sistema oferecer:

```bash
brew install git      # se você tem Homebrew
git --version         # sem Homebrew: o macOS oferece instalar
```

---

## Deu certo?

```bash
git --version
```

Saída esperada — o número pode variar:

```
git version 2.43.0
```

Apareceu a versão? Está instalado. ✅

---

## 2️⃣ Todo commit registra **quem** o fez

Antes do primeiro commit, diga ao Git quem é você:

```bash
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu-email@exemplo.com"
```

> 💡 `--global` quer dizer **todos os repositórios desta máquina**. Você faz isto uma vez na vida.

---

<!-- _class: lead -->

## ⚠️ O detalhe que custa caro

Use o **mesmo e-mail** aqui e na conta do GitHub.

É por ele que o GitHub reconhece os commits como seus.

**E-mail diferente = commits que não aparecem no seu perfil.**

---

## Mais duas configurações recomendadas

```bash
# "main" como nome do branch inicial (padrão moderno)
git config --global init.defaultBranch main

# VS Code como editor padrão do Git
git config --global core.editor "code --wait"
```

> 💡 A segunda só faz sentido se você usa o VS Code.

---

## Conferindo o que ficou gravado

```bash
git config --list
```

Procure estas linhas na saída:

```
user.name=Seu Nome Completo
user.email=seu-email@exemplo.com
init.defaultbranch=main
```

---

## 3️⃣ Criando a conta no GitHub

1. Acesse `github.com/signup`;
2. Use um e-mail que você **acessa com frequência** — de preferência o mesmo do `git config`;
3. Escolha o nome de usuário — **atenção ao próximo slide**;
4. Confirme o e-mail de verificação.

---

## O nome de usuário é o seu portfólio

Ele aparece em processos seletivos, não só aqui.

| ✅ Bom | ❌ Evite |
|---|---|
| `mariasilva` | `xX_destruidor_Xx` |
| `maria-silva-dev` | `mariazinha123gatinha` |
| `msilva2026` | `teste12345` |

---

<!-- _class: lead -->

## 🎓 Student Developer Pack

Estudantes têm acesso **gratuito** ao GitHub Pro e a dezenas de ferramentas pagas.

`education.github.com/pack`

Vale solicitar com o e-mail institucional.

---

## 4️⃣ O GitHub não aceita a sua senha

Para **enviar** código (`git push`), a sua máquina precisa provar que é você.

Senha comum **não funciona**. Usaremos um **Personal Access Token** — o PAT.

> 📢 **Padrão do curso:** HTTPS + token, o caminho mais simples para começar. SSH é a alternativa avançada, no fim do módulo.

---

<!-- _class: diagrama -->

## O caminho do token

![w:1126](img/caminho-do-token.svg)

---

## Gerando o token: três campos

**Settings → Developer settings → Personal access tokens → Tokens (classic)**

| Campo | O que preencher |
|---|---|
| **Note** | `notebook-pessoal` — para você lembrar de que máquina é |
| **Expiration** | 90 dias |
| **Scopes** | marque **apenas** `repo` |

---

<!-- _class: lead -->

## ⚠️ O token é uma senha

Ele aparece **uma única vez**. Copie na hora.

Não compartilhe, não poste em grupo
e **jamais** salve dentro de um repositório.

---

## Usando o token no `git push`

Na primeira vez, o Git vai perguntar:

```
Username: seu-usuario
Password: ghp_xxxxxxxxxxxx     ← o TOKEN, não a senha da conta
```

No Windows, o *Git Credential Manager* guarda sozinho. No Linux:

```bash
git config --global credential.helper store
```

---

## (Opcional) Autenticação por SSH

O método de quem já tem estrada:

```bash
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"
cat ~/.ssh/id_ed25519.pub
```

Cole a chave em **Settings → SSH and GPG keys → New SSH key** e passe a clonar pela URL `git@github.com:...`.

> 💡 Para este curso, **HTTPS + token basta**. Deixe o SSH para quando o básico estiver confortável.

---

<!-- _class: checkpoint lista-limpa -->

## ✅ Checkpoint do módulo

Ao final deste módulo você deve ter:

- ☐ Git instalado — `git --version` responde;
- ☐ Nome e e-mail configurados — aparecem em `git config --list`;
- ☐ Conta no GitHub criada e e-mail verificado;
- ☐ Token gerado e guardado em local seguro.

---

<!-- _class: lead -->

## ➡️ Próximo passo

**Módulo 3 — Comandos Básicos**

`init` · `status` · `add` · `commit` · `log` · `diff`
— o dia a dia do Git.

Traga o terminal já configurado.
