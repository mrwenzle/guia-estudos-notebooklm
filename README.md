# 📚 C# Mentor Lab: Estudo da Linguagem C# com NotebookLM

> Repositório desenvolvido para o Desafio de Projeto da **DIO (Digital Innovation One)**, utilizando o **Google NotebookLM** como um mentor interativo especialista em C# e ecossistema .NET.

---

## 📖 Sobre o Projeto & Contexto
Este projeto aplica técnicas de **Engenharia de Prompts** e **Aprendizado Ativo** para transformar o NotebookLM em uma ferramenta de mentoria técnica para C#. A proposta é ir além do estudo passivo, criando um ambiente reutilizável de estudo, auditoria de código e geração de exercícios práticos.

---

## 🎯 Objetivos
- [x] Criar uma base de conhecimento centralizada utilizando documentações oficiais e livros de referência.
- [x] Estruturar personas e diretrizes (System Prompts) para orientação técnica em C#.
- [x] Documentar o processo de engenharia de prompts, desafios e refinamentos (*Cicatrizes/Troubleshooting*).
- [x] Entregar um Miniguia de Estudos reutilizável com resumos, glossário e acervo de prompts.

---

## 📚 Fontes Utilizadas
A curadoria de fontes abertas e materiais de referência inclui:
1. **Documentação Oficial C# (Microsoft Docs)** – Guia de Linguagem C# e novos recursos.
2. **Documentação Oficial .NET Core Runtime API** – Referência de bibliotecas do sistema e execução.
3. **Apostila / Livro 1:** Fundamentos de Programação e C# Básico.
4. **Apostila / Livro 2:** Programação Orientada a Objetos (POO) avançada em C#.
5. **Apostila / Livro 3:** Estruturas de Dados e Algoritmos aplicados em C#.

---

## 🤖 Engenharia de Prompts

### Estrutura do System Prompt (`C# Mentor Lab`)
Para garantir respostas estruturadas, padronizadas nas convenções da Microsoft e orientadas ao estudo ativo, utilizamos o prompt armazenado em `prompts/01-system-prompt-mentor.md`.

---

## 🩹 Cicatrizes (Troubleshooting)

| Tentativa / Contexto | Prompt Utilizado | Problema Encontrado | Solução / Prompt Ajustado |
| :--- | :--- | :--- | :--- |
| **Explication de LINQ** | *"Me explica o que é LINQ e como usar."* | A resposta veio genérica, sem relação explícita com o desempenho e sem exemplos modernos de C#. | Adicionado papel (*C# Mentor Lab*), instrução de uso exclusivo das fontes do caderno e restrição para comparar Syntax vs Method Syntax. |
| **Review de Código** | *"Analise meu código C#."* | A IA apenas disse que o código estava bom, sem apontar boas práticas ou sugerir refatoração. | Criado o prompt `03-code-review.md` exigindo análise por critérios (POO, Clareza, Performance e Versão Refatorada). |
| **Teste de Prompt (LINQ e Performance)** | "Atue como o C# Mentor Lab. Explique LINQ, Sintaxe de Método vs Consulta e performance." | A resposta foi excelente tecnicamente, mas a IA omitiu um bloco de código no exemplo C e esqueceu de gerar o "Desafio Ativo" exigido no System Prompt. | Ajuste de Prompt: Reforcei a instrução adicionando no final: "Certifique-se de preencher todos os blocos de código e, OBRIGATORIAMENTE, finalize com o Desafio Ativo da Regra 4". |
---

## 📖 Miniguia de Estudos

### 📝 Resumo Estruturado: Boas Práticas de LINQ e Performance
1. **Deferred Execution (Execução Adiada):** Consultas LINQ não são processadas na hora da declaração. Evite usar `.ToList()` ou `.ToArray()` antes da hora para economizar alocações de memória.
2. **IEnumerable vs IQueryable:** Use `IEnumerable` para coleções já em memória. Use `IQueryable` para consultas ao banco de dados, para que o filtro seja traduzido para SQL em vez de puxar toda a tabela para a memória.
3. **Avaliação de Variáveis no Loop:** Avalie propriedades dinâmicas (ex: `DateTime.Today`) **antes** da query LINQ e passe o resultado em uma variável, evitando recálculos desnecessários durante a iteração.
4. **Operadores Eficientes:** Use `TakeWhile` no lugar de `Where` em listas ordenadas para evitar varreduras completas desnecessárias, e prefira `First()` a `Single()` caso não precise validar a unicidade de registros em tempo de execução.

### 📕 Glossário Técnico C#
- **CLR (Common Language Runtime):** Ambiente de execução virtual do .NET.
- **LINQ (Language Integrated Query):** Sintaxe unificada para consulta de dados em coleções, bancos ou XML.
- **Record Types:** Tipos por referência imutáveis introduzidos no C# 9 focados em dados.
- **Async/Await:** Padrão assíncrono baseado em tarefas (`Task`) para não bloquear a thread principal.

### 💡 Prompts Reutilizáveis
- `prompts/01-system-prompt-mentor.md`: Definição de persona do mentor.
- `prompts/02-explicacao-conceito.md`: Explicação profunda de conceitos técnicos.
- `prompts/03-code-review.md`: Análise e refatoração de trechos de código.
- `prompts/04-gerador-desafios.md`: Criação de exercícios e cenários práticos.

---

## 🚀 Conclusão
O uso do NotebookLM como mentor reduziu o tempo de consulta e permitiu um estudo focado, contextualizado e confiável nas fontes selecionadas. Este modelo serve como um **template reutilizável** para qualquer outra linguagem ou tecnologia.
