# Exercício 05 — Repositórios das Disciplinas

> 📚 Fazer após o [Módulo 7](../07-boas-praticas/README.md)
> 🎯 Objetivo: montar os repositórios **oficiais** que você usará o semestre todo em JavaScript e Java (OO)
> ⭐ **Este exercício vale como primeira entrega das disciplinas!**

## Enunciado

Você criará **dois repositórios**, um para cada disciplina, aplicando todas as boas práticas do Módulo 7.

### Repositório 1: `javascript-2026-2`

1. Crie o repositório no GitHub e clone-o (ou crie local e conecte — você escolhe o caminho);
2. Adicione um **`.gitignore`** adequado a Node.js (use o modelo do Módulo 7);
3. Crie um **`README.md`** contendo: seu nome, a disciplina, como executar os programas (`node arquivo.js`) e a estrutura de pastas;
4. Crie a pasta `aula-01/` com um arquivo `ola-mundo.js`:

   ```javascript
   console.log("Olá, mundo! Repositório de JavaScript pronto.");
   ```

5. Commits organizados (sugestão: um para o `.gitignore`, um para o README, um para a aula-01) e push.

### Repositório 2: `java-oo-2026-2`

6. Repita o processo com o `.gitignore` de **Java** e um `README.md` equivalente;
7. Crie a pasta `aula-01/` com um arquivo `OlaMundo.java`:

   ```java
   public class OlaMundo {
       public static void main(String[] args) {
           System.out.println("Olá, mundo! Repositório de Java pronto.");
       }
   }
   ```

8. **Importante:** compile o arquivo (`javac OlaMundo.java`), rode `git status` e confirme que o `.class` gerado **não aparece** para ser commitado — se aparecer, seu `.gitignore` está errado;
9. Commits organizados e push.

### Entrega

10. Envie ao professor (pelo canal combinado) os links dos dois repositórios:
    - `https://github.com/SEU-USUARIO/javascript-2026-2`
    - `https://github.com/SEU-USUARIO/java-oo-2026-2`

## ✅ Critérios de avaliação

| Critério | Verificação |
|----------|-------------|
| README completo | Nome, disciplina, instruções de execução e estrutura |
| `.gitignore` correto | `.class`/`node_modules` não aparecem no repositório |
| Estrutura de pastas | `aula-01/` com nomes sem espaços/acentos |
| Mensagens de commit | Descritivas, verbo no presente |
| Código funcional | Os "Olá, mundo" executam sem erro |
| Push realizado | Tudo visível no GitHub pelo navegador |

> 🚀 **A partir de agora**, todos os exemplos e exercícios das aulas serão commitados nesses repositórios, com uma pasta por aula. O histórico de commits faz parte da avaliação contínua — commits frequentes contam a favor!
