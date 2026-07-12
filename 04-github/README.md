# Módulo 4 — Trabalhando com o GitHub

> ⏱️ Duração estimada: 1 hora
> 📋 Pré-requisitos: [Módulo 3](../03-comandos-basicos/README.md) e conta no GitHub configurada ([Módulo 2](../02-instalacao-config/README.md))

Até agora, tudo estava só na sua máquina. Neste módulo, seus repositórios ganham uma cópia na nuvem: backup, portfólio e porta para colaboração.

## 4.1 Repositório local × repositório remoto

```
        SUA MÁQUINA                              GITHUB (nuvem)
┌─────────────────────────┐              ┌─────────────────────────┐
│   Repositório LOCAL     │   git push   │   Repositório REMOTO    │
│                         │─────────────▶│                         │
│   (pasta ola-git com    │              │   (github.com/voce/     │
│    a pasta .git)        │◀─────────────│    ola-git)             │
│                         │   git pull   │                         │
└─────────────────────────┘              └─────────────────────────┘
```

- **`push`** = empurrar seus commits para o remoto (subir);
- **`pull`** = puxar commits do remoto para sua máquina (baixar).

O remoto **não se atualiza sozinho**: commitar localmente não envia nada ao GitHub. Enviar é sempre um ato explícito (`push`).

## 4.2 Criando um repositório no GitHub

1. Logado no GitHub, clique no **`+`** (canto superior direito) → **New repository**;
2. Preencha:
   - **Repository name:** `ola-git` (use o mesmo nome da pasta local, por organização);
   - **Description:** opcional, mas recomendado;
   - **Public** ou **Private:** para exercícios da disciplina, use **Public** (ou conforme orientação do professor);
   - ⚠️ **NÃO marque** "Add a README file" — como já temos um repositório local com commits, o remoto deve nascer **vazio**;
3. Clique em **Create repository**.

O GitHub mostrará uma página com instruções. Vamos usar a seção *"…or push an existing repository from the command line"*.

## 4.3 Conectando o local ao remoto

No terminal, dentro da pasta `ola-git` do módulo anterior:

```bash
git remote add origin https://github.com/SEU-USUARIO/ola-git.git
```

Este comando **não envia nada** — apenas registra o "endereço" do remoto, dando a ele o apelido **`origin`** (o nome padrão para o remoto principal).

Confira:

```bash
git remote -v
```

```
origin  https://github.com/SEU-USUARIO/ola-git.git (fetch)
origin  https://github.com/SEU-USUARIO/ola-git.git (push)
```

## 4.4 `git push` — enviando os commits

```bash
git push -u origin main
```

Na primeira vez, o Git pedirá autenticação:

- **Username:** seu usuário do GitHub;
- **Password:** o **token** criado no Módulo 2 (não a senha da conta!).

Saída esperada:

```
Enumerating objects: 9, done.
...
To https://github.com/SEU-USUARIO/ola-git.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

🎉 Atualize a página do repositório no navegador: seus arquivos e o histórico de commits estão lá!

> 💡 O `-u` (de *upstream*) cria um vínculo entre o `main` local e o `main` remoto. Ele só é necessário **no primeiro push** — depois disso, basta `git push`.

## 4.5 `git pull` — baixando atualizações

O `pull` traz para sua máquina commits que existem no remoto mas não no local. Isso acontece quando:

- Você editou algo **pela interface do GitHub** (é possível editar arquivos direto no site);
- Você trabalha em **duas máquinas** (casa e faculdade);
- **Outra pessoa** enviou commits para o repositório.

Vamos simular: no GitHub, abra o repositório `ola-git`, clique no arquivo `index.js` → ícone de **lápis** (Edit) → adicione uma linha de comentário → **Commit changes**.

Agora sua máquina está **desatualizada** em relação ao remoto. Baixe a novidade:

```bash
git pull
```

```
Updating f4e5d6c..9a8b7c6
Fast-forward
 index.js | 1 +
 1 file changed, 1 insertion(+)
```

> 📏 **Regra de ouro para o semestre:** trabalhando em mais de um computador (ou em equipe), **sempre comece a sessão com `git pull` e termine com `git push`**. Isso evita a maioria dos conflitos.

## 4.6 `git clone` — baixando um repositório completo

O `clone` copia um repositório remoto inteiro (arquivos + todo o histórico) para sua máquina. É assim que você vai:

- Baixar este material do curso;
- Baixar os repositórios de exemplo das aulas de JS e Java;
- Começar a trabalhar em qualquer projeto existente.

```bash
# Sintaxe: git clone <url>
git clone https://github.com/SEU-USUARIO/ola-git.git

# Isso cria a pasta ola-git, já com .git configurado
cd ola-git
git remote -v   # o "origin" já vem configurado automaticamente!
```

A URL é obtida no botão verde **`<> Code`** na página do repositório.

> 💡 **`clone` × `pull`:** o `clone` é feito **uma vez**, para obter o repositório. O `pull` é feito **sempre**, para atualizar um repositório que você já tem.

## 4.7 O fluxo completo do dia a dia

A partir de agora, sua rotina de trabalho nas disciplinas será:

```bash
# ── Começando a sessão de estudo ──
cd meu-repositorio
git pull                          # 1. atualiza com o remoto

# ── Trabalhando ──
# ... programa, edita, testa ...
git status                        # 2. confere o que mudou
git add .                         # 3. prepara as mudanças
git commit -m "Resolve exercício 3 de laços"   # 4. commita

# ... continua trabalhando, mais commits ...

# ── Encerrando a sessão ──
git push                          # 5. envia tudo para o GitHub
```

> ⚠️ **Commit sem push não conta como entrega!** Se você commitou mas não deu push, o professor (e o GitHub) não veem nada. Confira sempre no navegador se o trabalho subiu.

## 4.8 Explorando a interface do GitHub

Na página de um repositório, localize:

| Elemento | Onde | Para quê |
|----------|------|----------|
| Lista de arquivos | Centro da página | Navegar pelo código |
| Botão **`<> Code`** | Verde, à direita | Copiar a URL para clone |
| **Commits** (🕑 número) | Acima da lista de arquivos | Ver o histórico completo, com diffs |
| **README.md** | Renderizado abaixo dos arquivos | A "capa" do projeto |
| **Issues** | Aba superior | Reportar problemas e tirar dúvidas (Módulo 6) |
| **Settings** | Aba superior | Renomear, tornar privado, apagar o repo |

## ✅ Checkpoint do módulo

1. Qual a diferença entre `push` e `pull`? E entre `clone` e `pull`?
2. O que é o `origin`?
3. Por que commitar não basta para "entregar" um trabalho?
4. Como você baixaria o repositório de exemplos da disciplina?

🏋️ **Agora faça o [Exercício 02](../exercicios/exercicio-02.md)!**

---

⬅️ [Módulo 3 — Comandos Básicos](../03-comandos-basicos/README.md) | ➡️ [Módulo 5 — Branches](../05-branches/README.md)
