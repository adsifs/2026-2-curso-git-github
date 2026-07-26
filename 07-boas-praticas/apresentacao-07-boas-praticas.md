---
marp: true
theme: trilha
paginate: true
lang: pt-BR
footer: '📚 Curso de Git e GitHub · Módulo 7'
---

<!-- _class: capa -->

<div class="emoji">🏆</div>

# Boas Práticas

## Módulo 7 · Curso de Git e GitHub

<div class="meta">⏱️ 30 minutos &nbsp;·&nbsp; 📋 Requer o Módulo 6</div>

---

## Roteiro

Saber os comandos é metade do caminho. A outra metade é usá-los **bem**.

1. Mensagens de commit que prestam
2. `.gitignore` — o que **não** versionar
3. README — a capa do projeto
4. Organização de pastas e nomes
5. O checklist de qualidade

---

<!-- _class: lead -->

## A mensagem de commit é uma carta para o futuro

Para o seu "eu" daqui a três meses.

Para o colega que abrir o repositório.

Para quem for revisar o seu trabalho.

---

## Dois `git log`, lado a lado

| ❌ Antes deste módulo | ✅ Depois |
|---|---|
| `arrumei` | `Corrige cálculo de média com lista vazia` |
| `agora vai` | `Adiciona validação de entrada no formulário` |
| `mudanças` | `Resolve exercício 4 — herança em Java` |
| `asdfgh` | `Remove código duplicado da classe Aluno` |
| `commit final 2` | `Adiciona README com instruções de execução` |

---

## Quatro regras práticas

1. **Diga o que a mudança faz.** Complete a frase *"Este commit…"* → *"…adiciona validação de CPF"*;
2. **Verbo no presente:** *Adiciona*, *Corrige*, *Remove*, *Atualiza*, *Refatora*;
3. **Específico, mas curto** — até ~50 caracteres na primeira linha;
4. **Um commit = uma mudança lógica.** Fez o exercício 3 e o 4? Dois commits.

---

<!-- _class: lista-limpa -->

## Com que frequência commitar?

- ❌ **Um commit gigante no fim do dia**, com 15 arquivos — impossível de revisar ou reverter;
- ❌ **Um commit por linha alterada** — poluição pura;
- ✅ **Um commit a cada passo concluído** — terminou uma função que funciona? Commit. Resolveu um exercício? Commit.

> 💡 Dez commits distribuídos ao longo da semana contam uma história muito melhor do que um único *"trabalho completo"* na véspera.

---

<!-- _class: lista-limpa -->

## `.gitignore` — o que **não** versionar

- 📦 **Dependências** recuperáveis — `node_modules/` chega a ter milhares de arquivos;
- ⚙️ **Arquivos gerados** por compilação — `*.class`, `build/`, `dist/`, `target/`;
- 🔐 **Segredos** — senhas, tokens, arquivos `.env`;
- 🖥️ **Configuração pessoal** de editor e lixo do sistema — `.idea/`, `.DS_Store`.

---

## Um `.gitignore` na prática

```gitignore
node_modules/     # recuperável com "npm install"
.env              # segredos nunca entram no repositório
*.log
.vscode/
.idea/
.DS_Store
```

Fica na **raiz** do repositório — e ele próprio **deve ser commitado**.

> 💡 O site `gitignore.io` gera um pronto para qualquer combinação de linguagem, IDE e sistema.

---

<!-- _class: lead -->

## ⚠️ O `.gitignore` não apaga o passado

Ele **não** afeta arquivos que já foram commitados.

Se o `node_modules/` entrou por engano, é preciso tirá-lo do rastreamento primeiro:

`git rm -r --cached node_modules/`

---

## README — a capa do projeto

É a primeira coisa que qualquer pessoa vê ao abrir o seu repositório. **Todo repositório deve ter um.**

Ele responde três perguntas, nessa ordem:

1. **O que é isto?**
2. **Como eu executo?**
3. **Quem fez?**

---

## O modelo mínimo

```markdown
# Nome do Projeto
Breve descrição do que este repositório contém.
## 🛠️ Tecnologias
- Java 21 / Node.js 22
## 🚀 Como executar
    node index.js
## 📁 Estrutura
- `aula-01/` — variáveis e tipos
## 👤 Autor
Seu Nome — [seu-usuario](https://github.com/seu-usuario)
```

> 💡 Dez linhas já fazem um README decente. O que não pode é não ter nenhum.

---

## Organização: uma pasta por aula

```
javascript-2026/
├── .gitignore
├── README.md
├── aula-01-introducao/
│   ├── exemplo-01.js
│   └── exercicios/
├── aula-02-funcoes/
└── trabalhos/
    └── trabalho-01/
```

---

<!-- _class: lista-limpa -->

## Nomes: sem espaço, sem acento

- 📂 **Pasta por aula**, numerada e descritiva: `aula-03-arrays` — não `aula3`, nem `Aula 3 - Arrays!!`;
- 🔤 **Sem espaços e sem acentos** — use `-` ou `camelCase`. Espaço e acento dão dor de cabeça no terminal;
- 📝 **Commit por exercício ou por aula**, dizendo o quê: `"Resolve exercícios 1-3 da aula 05 (arrays)"`.

---

<!-- _class: checkpoint lista-limpa -->

## ✅ Checklist de qualidade

Antes de considerar o repositório apresentável:

- ☐ Tem `README.md` dizendo o que é e como executar;
- ☐ Tem `.gitignore` adequado à linguagem;
- ☐ **Não** contém `node_modules/`, `.class`, pastas de build ou segredos;
- ☐ As mensagens de commit descrevem as mudanças;
- ☐ Pastas organizadas, nomes sem espaço e sem acento;
- ☐ O `push` foi dado — confira **pelo navegador**.

---

<!-- _class: checkpoint -->

## ✅ Checkpoint do módulo

1. O que faz uma mensagem de commit ser boa?
2. Por que o `node_modules/` nunca deve ser commitado?
3. O que acontece ao adicionar ao `.gitignore` um arquivo já commitado?
4. Quais os itens mínimos de um bom README?

---

<!-- _class: lead -->

## 🏁 Fim do curso

Você saiu de *"trabalho_FINAL_AGORA_VAI.js"*
e chegou a **Pull Request com revisão**.

**Exercício 05** — monte os seus repositórios de verdade.

`exercicios/exercicio-05.md`

Agora é usar. Todo dia, em todo projeto.
