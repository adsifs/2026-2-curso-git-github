# Módulo 7 — Boas Práticas

> ⏱️ Duração estimada: 30 minutos
> 📋 Pré-requisitos: [Módulo 6](../06-fluxo-de-trabalho/README.md)

Saber os comandos é metade do caminho. A outra metade é usá-los **bem** — e é isso que diferencia um repositório profissional de um amontoado de arquivos.

## 7.1 Mensagens de commit que prestam

A mensagem de commit é uma carta para o futuro: para o seu "eu" daqui a três meses, para o colega de equipe, para o professor corrigindo. Compare:

```
❌ git log de quem não leu este módulo:        ✅ git log de quem leu:

  "arrumei"                                       "Corrige cálculo de média com lista vazia"
  "agora vai"                                     "Adiciona validação de entrada no formulário"
  "mudanças"                                      "Resolve exercício 4 - herança em Java"
  "asdfgh"                                        "Remove código duplicado da classe Aluno"
  "commit final"                                  "Adiciona README com instruções de execução"
  "commit final 2"
```

### Regras práticas

1. **Diga O QUE a mudança faz**, não "mexi em coisas": complete mentalmente a frase *"Este commit..."* → *"...adiciona validação de CPF"*;
2. **Comece com verbo no presente:** *Adiciona*, *Corrige*, *Remove*, *Atualiza*, *Refatora*;
3. **Seja específico, mas curto:** até ~50 caracteres na primeira linha;
4. **Um commit = uma mudança lógica.** Fez o exercício 3 e o 4? Dois commits. Isso torna o histórico legível e permite reverter mudanças isoladamente.

### Frequência de commits

- ❌ **Um commit gigante no fim do dia** com 15 arquivos: impossível de revisar ou reverter;
- ❌ **Um commit por linha alterada:** poluição;
- ✅ **Um commit a cada passo concluído:** terminou uma função que funciona? Commit. Resolveu um exercício? Commit.

> 🎓 **Na disciplina:** o histórico de commits mostra seu processo de trabalho. Dez commits distribuídos na semana contam uma história muito melhor que um commit "trabalho completo" às 23h58 do prazo.

## 7.2 `.gitignore` — o que NÃO versionar

Nem tudo que está na pasta do projeto deve ir para o repositório. **Não** se versiona:

- 📦 **Dependências** que podem ser baixadas de novo (`node_modules/` — pode ter *milhares* de arquivos!);
- ⚙️ **Arquivos gerados** por compilação (`*.class` do Java, pastas `build/`, `dist/`, `target/`);
- 🔐 **Segredos**: senhas, tokens, arquivos `.env`;
- 🖥️ **Configurações pessoais** de editor (`.idea/`, `.vscode/`) e lixo do sistema (`.DS_Store`, `Thumbs.db`).

A solução é o arquivo **`.gitignore`**: uma lista de padrões que o Git deve ignorar. Ele fica na **raiz** do repositório (e sim, ele próprio deve ser commitado).

### `.gitignore` para a disciplina de JavaScript (Node.js)

```gitignore
# Dependências (recuperáveis com "npm install")
node_modules/

# Variáveis de ambiente e segredos
.env
.env.local

# Logs
*.log
npm-debug.log*

# Configurações de editor e sistema operacional
.vscode/
.idea/
.DS_Store
Thumbs.db
```

### `.gitignore` para a disciplina de Java

```gitignore
# Arquivos compilados
*.class
*.jar
*.war

# Pastas de build
target/
build/
out/
bin/

# Arquivos de IDE
.idea/
*.iml
.vscode/
.settings/
.classpath
.project

# Sistema operacional
.DS_Store
Thumbs.db
```

> 💡 O site <https://gitignore.io> gera `.gitignore` prontos para qualquer combinação de linguagem + IDE + sistema. O GitHub também oferece templates ao criar um repositório.

> ⚠️ **O `.gitignore` não afeta arquivos já commitados.** Se você commitou o `node_modules/` por engano, precisa removê-lo do rastreamento: `git rm -r --cached node_modules/`, commit, e só então o ignore passa a valer.

## 7.3 README — a capa do seu projeto

O `README.md` é a primeira coisa que qualquer pessoa vê ao abrir seu repositório. Todo repositório da disciplina deve ter um. Modelo mínimo:

```markdown
# Nome do Projeto

Breve descrição: o que este projeto/repositório contém.

## 🛠️ Tecnologias

- Java 21 / Node.js 22 (o que você estiver usando)

## 🚀 Como executar

​```bash
# JavaScript:
node index.js

# Java:
javac Main.java && java Main
​```

## 📁 Estrutura

- `aula-01/` — variáveis e tipos
- `aula-02/` — estruturas de controle
- ...

## 👤 Autor

Seu Nome — [seu-usuario](https://github.com/seu-usuario)
```

## 7.4 Organização dos repositórios da disciplina

Estrutura recomendada para os repositórios de JS e Java deste semestre:

```
javascript-2026-1/                     java-oo-2026-1/
├── .gitignore                         ├── .gitignore
├── README.md                          ├── README.md
├── aula-01-introducao/                ├── aula-01-classes-objetos/
│   ├── exemplo-01.js                  │   ├── Pessoa.java
│   └── exercicios/                    │   └── Main.java
│       ├── ex01.js                    ├── aula-02-encapsulamento/
│       └── ex02.js                    │   └── ...
├── aula-02-funcoes/                   └── trabalhos/
│   └── ...                                └── trabalho-01/
└── trabalhos/
    └── trabalho-01/
```

Convenções:

- 📂 **Uma pasta por aula**, com nome numerado e descritivo (`aula-03-arrays`, não `aula3` nem `Aula 3 - Arrays!!`);
- 🔤 Nomes de pastas/arquivos **sem espaços e sem acentos** (use `-` ou `camelCase`) — espaços e acentos causam dor de cabeça no terminal;
- 📝 Commit **por exercício ou por aula**, com mensagem indicando o quê: `"Resolve exercícios 1-3 da aula 05 (arrays)"`.

## 7.5 Checklist de qualidade do repositório

Antes de considerar seu repositório "apresentável":

- [ ] Tem `README.md` explicando o que é e como executar;
- [ ] Tem `.gitignore` adequado à linguagem;
- [ ] **Não** contém `node_modules/`, `.class`, pastas de build ou segredos;
- [ ] Mensagens de commit descrevem as mudanças;
- [ ] Estrutura de pastas organizada e nomes sem espaços/acentos;
- [ ] O `git push` foi dado — confira **pelo navegador** que está tudo lá.

## ✅ Checkpoint do módulo

1. O que faz uma mensagem de commit ser boa?
2. Por que o `node_modules/` nunca deve ser commitado?
3. O que acontece se você adicionar ao `.gitignore` um arquivo já commitado?
4. Quais os itens mínimos de um bom README?

🏋️ **Agora faça o [Exercício 05](../exercicios/exercicio-05.md)** — nele você montará os repositórios oficiais das disciplinas!

---

⬅️ [Módulo 6 — Fluxo de Trabalho](../06-fluxo-de-trabalho/README.md) | 🏠 [Voltar ao início](../README.md)
