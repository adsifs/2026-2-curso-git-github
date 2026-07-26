---
marp: true
theme: trilha
paginate: true
lang: pt-BR
footer: '📚 Curso de Git e GitHub · Módulo 1'
---

<!-- _class: capa -->

<div class="emoji">📚</div>

# Conceitos Fundamentais

## Módulo 1 · Curso de Git e GitHub

<div class="meta">⏱️ 30 minutos &nbsp;·&nbsp; 📋 Nenhum pré-requisito</div>

---

## Roteiro

1. O problema: **a vida sem controle de versão**
2. O que é um **sistema de controle de versão**
3. O que é o **Git** — e os três estados de um arquivo
4. O que é o **GitHub** — e por que não é a mesma coisa
5. O **vocabulário** que você vai usar o curso inteiro

---

## Já viveu esta cena?

```
📁 TrabalhoFinal/
├── trabalho.js
├── trabalho_v2.js
├── trabalho_v2_corrigido.js
├── trabalho_FINAL.js
├── trabalho_FINAL_AGORA_VAI.js
└── trabalho_FINAL_entregar_ESSE.js
```

---

<!-- _class: lista-limpa -->

## Por que isso não funciona

- ❌ Qual é a versão mais recente? **Ninguém sabe**;
- ❌ O que mudou da `v2` para a `v2_corrigido`? **Impossível dizer**;
- ❌ Se o HD queimar, **perdeu tudo**;
- ❌ Dois colegas editando o mesmo arquivo? **Um sobrescreve o outro**;
- ❌ *"Funcionava ontem e hoje não funciona"* — e **não há como voltar atrás**.

---

<!-- _class: lista-limpa -->

## O que é controle de versão

Um software que **registra as alterações nos arquivos ao longo do tempo**:

- 📸 **Fotografar** o projeto num momento — cada foto é um *commit*;
- ⏪ **Voltar** para qualquer versão anterior;
- 🔍 **Comparar** versões: o que mudou, quando e quem mudou;
- 👥 **Colaborar** sem sobrescrever o trabalho do outro.

---

<!-- _class: lead -->

## 💡 Pense nos *save points*

Você salva o progresso em pontos importantes e, se algo der errado, volta ao último save.

**O Git são os save points do seu código** — com a diferença de que você pode voltar a **qualquer** save, não só ao último.

---

## O que é o Git?

O sistema de controle de versão **mais usado no mundo**.

Criado em **2005** por **Linus Torvalds** — o mesmo criador do Linux — para gerenciar o desenvolvimento do kernel.

> 💡 Ou seja: ele nasceu para dar conta de milhares de pessoas mexendo no mesmo projeto ao mesmo tempo. O seu projeto vai ser tranquilo para ele.

---

<!-- _class: lista-limpa -->

## Git em quatro características

- 🖥️ **Roda na sua máquina** — você não precisa de internet para usar o Git;
- 🆓 **Gratuito e open source**;
- ⚡ **Rápido** — operações em frações de segundo, mesmo em projetos gigantes;
- 🌎 **Padrão de mercado** — praticamente toda empresa de software usa Git.

---

<!-- _class: diagrama -->

## Os três estados de um arquivo

![w:1140](img/tres-estados.svg)

---

## Os três estados, em palavras

1. **Diretório de trabalho** — a pasta do projeto, onde você cria e edita normalmente;
2. **Área de stage** — a área de preparação: o que vai entrar na próxima foto;
3. **Repositório** — o histórico permanente, guardado na pasta oculta `.git`.

> ⚠️ Este é **o conceito mais importante do curso**. Se ficar sólido agora, todo o resto vira consequência.

---

<!-- _class: lead lista-limpa -->

## 💡 A foto de grupo

- 🎉 **Diretório de trabalho** — a festa toda, com todo mundo circulando
- 🎬 **Área de stage** — o palco, onde você posiciona quem vai sair na foto
- 📸 **O commit** — o clique da câmera: a foto vai para o **álbum**, para sempre

---

## Git ≠ GitHub

| | Git | GitHub |
|---|---|---|
| **O que é** | Software de controle de versão | Site/plataforma na internet |
| **Onde roda** | Na sua máquina | Na nuvem |
| **Precisa de internet?** | Não | Sim |
| **Quem mantém** | Comunidade open source | Microsoft |

> ⚠️ Há alternativas ao GitHub — **GitLab, Bitbucket, Codeberg** — mas todas usam o **mesmo Git** por baixo.

---

<!-- _class: lead -->

## 💡 Fotos e Google Fotos

O Git está para o GitHub assim como as **fotos** estão para o **Google Fotos**.

Você tira fotos com a sua câmera — **Git**, na sua máquina.
E pode enviá-las para a nuvem — **GitHub** — para ter backup e compartilhar.

---

<!-- _class: lista-limpa -->

## O que o GitHub adiciona por cima do Git

- 🌐 **Backup** dos seus repositórios na nuvem;
- 👥 **Colaboração** — Pull Requests, Issues, revisão de código;
- 📢 **Portfólio público** — recrutadores olham o GitHub de candidatos;
- 🤝 **Acesso** a milhões de projetos open source.

---

<!-- _class: tabela-densa -->

## Vocabulário essencial

| Termo | Significado |
|---|---|
| **Repositório** (repo) | A pasta do projeto + todo o seu histórico de versões |
| **Commit** | Uma "foto" do projeto, com autor, data e mensagem |
| **Stage** | Área de preparação dos arquivos para o próximo commit |
| **Branch** | Linha de desenvolvimento independente (Módulo 5) |
| **Remote** | Cópia do repositório hospedada em outro lugar |
| **Clone** | Baixar uma cópia completa de um repositório remoto |
| **Push** | Enviar seus commits locais para o remoto |
| **Pull** | Trazer commits do remoto para a sua máquina |

---

<!-- _class: checkpoint -->

## ✅ Checkpoint do módulo

Antes de avançar, você deve saber responder:

1. Que problemas o controle de versão resolve?
2. Qual a diferença entre Git e GitHub?
3. Quais são os três estados de um arquivo no Git?
4. O que é um commit?

---

<!-- _class: lead -->

## ➡️ Próximo passo

**Módulo 2 — Instalação e Configuração**

Instalar o Git, configurar a sua identidade e criar a conta no GitHub.

`github.com/jreluiz/curso-git-github`
