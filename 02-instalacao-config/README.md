# Módulo 2 — Instalação e Configuração

> ⏱️ Duração estimada: 40 minutos
> 📋 Pré-requisitos: [Módulo 1](../01-conceitos/README.md)
> 🎬 Slides da aula: [apresentacao-02-instalacao-config.pdf](apresentacao-02-instalacao-config.pdf)

## 2.1 Instalando o Git

### Windows

1. Acesse <https://git-scm.com/download/win>;
2. Baixe o instalador e execute;
3. **Pode aceitar todas as opções padrão** clicando em *Next* (elas são boas para iniciantes);
4. Ao final, você terá o **Git Bash** instalado — um terminal que usaremos no curso.

> 💡 No Windows, use sempre o **Git Bash** para os comandos deste curso. Ele aceita os mesmos comandos do Linux/Mac, então todos da turma verão a mesma coisa.

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

### macOS

```bash
# Se tiver o Homebrew:
brew install git

# Ou simplesmente digite "git" no terminal:
# o macOS oferecerá instalar as ferramentas de linha de comando
git --version
```

### Verificando a instalação

Abra o terminal (Git Bash no Windows) e digite:

```bash
git --version
```

Saída esperada (o número pode variar):

```
git version 2.43.0
```

Se apareceu a versão, está instalado. ✅

## 2.2 Configurando sua identidade

Todo commit registra **quem** o fez. Antes do primeiro commit, configure seu nome e e-mail:

```bash
git config --global user.name "Seu Nome Completo"
git config --global user.email "seu-email@exemplo.com"
```

> ⚠️ **Importante:** use o **mesmo e-mail** que você vai usar na conta do GitHub. É assim que o GitHub associa os commits ao seu perfil.

Duas configurações extras recomendadas:

```bash
# Define "main" como nome do branch inicial (padrão moderno)
git config --global init.defaultBranch main

# Define o VS Code como editor padrão do Git (se você usa VS Code)
git config --global core.editor "code --wait"
```

Para conferir tudo o que foi configurado:

```bash
git config --list
```

> 💡 O `--global` significa que a configuração vale para **todos os repositórios** da sua máquina. Você só precisa fazer isso **uma vez**.

## 2.3 Criando sua conta no GitHub

1. Acesse <https://github.com/signup>;
2. Use um **e-mail que você acessa com frequência** (de preferência o mesmo do `git config`);
3. Escolha um nome de usuário **profissional** — ele vai aparecer no seu portfólio e em processos seletivos:
   - ✅ Bom: `mariasilva`, `maria-silva-dev`, `msilva2026`
   - ❌ Evite: `xX_destruidor_Xx`, `mariazinha123gatinha`
4. Confirme o e-mail de verificação.

> 🎓 **Dica:** estudantes têm acesso gratuito ao **GitHub Student Developer Pack** (<https://education.github.com/pack>), que inclui GitHub Pro e dezenas de ferramentas pagas. Vale a pena solicitar com o e-mail institucional.

## 2.4 Autenticação: conectando sua máquina ao GitHub

Para **enviar** código ao GitHub (`push`), sua máquina precisa provar que é você. O GitHub **não aceita senha comum** — usaremos um **Personal Access Token (PAT)**.

> 📢 **Padrão da disciplina:** usaremos **HTTPS + token**, que é o método mais simples para começar. (SSH é uma alternativa mais avançada, descrita no final do módulo como conteúdo opcional.)

### Criando seu token

1. No GitHub, clique na sua foto (canto superior direito) → **Settings**;
2. No menu lateral, desça até **Developer settings** (última opção);
3. Clique em **Personal access tokens** → **Tokens (classic)**;
4. **Generate new token** → **Generate new token (classic)**;
5. Preencha:
   - **Note:** `notebook-faculdade` (um nome para você lembrar de onde é);
   - **Expiration:** 90 dias (ou "No expiration" durante o semestre);
   - **Scopes:** marque apenas **`repo`** (acesso completo aos seus repositórios);
6. Clique em **Generate token**;
7. **COPIE O TOKEN AGORA** e guarde em local seguro (gerenciador de senhas, arquivo pessoal). Ele **nunca mais será exibido**.

> ⚠️ **O token é uma senha.** Não compartilhe, não poste em grupo da turma, e **jamais** o salve dentro de um repositório.

### Usando o token

Na primeira vez que você fizer um `git push` (Módulo 4), o Git pedirá:

- **Username:** seu usuário do GitHub;
- **Password:** **cole o token** (não é a senha da conta!).

No Windows, o *Git Credential Manager* (instalado junto com o Git) guardará o token automaticamente — você só digita uma vez. No Linux, para não digitar sempre:

```bash
git config --global credential.helper store
```

## 2.5 (Opcional) Autenticação via SSH

Se você quiser o método usado por desenvolvedores experientes:

```bash
# 1. Gerar o par de chaves (aceite os padrões com Enter)
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"

# 2. Exibir a chave pública para copiar
cat ~/.ssh/id_ed25519.pub
```

Depois, no GitHub: **Settings → SSH and GPG keys → New SSH key**, cole a chave e salve. Ao clonar repositórios, use a URL SSH (`git@github.com:...`) em vez da HTTPS.

> 💡 Para este curso, **HTTPS + token é suficiente**. Deixe o SSH para quando estiver confortável com o básico.

## ✅ Checkpoint do módulo

Você deve ter, ao final deste módulo:

- [ ] Git instalado (`git --version` funciona);
- [ ] Nome e e-mail configurados (`git config --list` mostra `user.name` e `user.email`);
- [ ] Conta no GitHub criada e e-mail verificado;
- [ ] Token de acesso criado e guardado em local seguro.

---

⬅️ [Módulo 1 — Conceitos](../01-conceitos/README.md) | ➡️ [Módulo 3 — Comandos Básicos](../03-comandos-basicos/README.md)
