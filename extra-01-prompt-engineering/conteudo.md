# Prompt Engineering

## Introdução

### O que é sua importância?

Engenharia que busca a melhor forma de instruções para IA para melhores resultados e de forma mais eficiente

- Desenvolver e manter
- Explorar possibilidades
- Automatizar tarefas repetitivas
- Obter soluções rápidas
- Auxiliar em processos complexos de desenvolvimento
- Aprimorar a colaboração

### Utilização e possibilidades

- Documentação e Design Docs
- Implementação
- Code Review
- Mastermind e brainstorming - colocar dois especialistas para discutir a melhor solução

### Documentação e Design Docs

- Requisitos e Produto // TRD, PRD, FRD, User Stories
- Design e Arquitetura // System Design (HL), Low-Level Design (LLD), C4
- Decisões Técnicas // ADRs, RFCs
- Engineering Guidelines // Coding Standards, Code Review, Testing, CI/CD, Security
- Ops e Infra // Runbook, Playbook, Infrastructure Design Document, Post-morten

### Implementação

- Exploração: "Trabalhar com prompts específicos gera insights para elaborar soluções mais eficazes e inovadoras."
- Contextualização: "torna mais claro o que desenvolver, o que é esperado e quais são os critérios de sucesso."
- Tarefas e Plano de ação: "To-do list, passos, etapas, divisão de tarefas, etc, gera resultados melhores e mais organizados, tanto para IA quanto para o proprio entendimento."
- Workflow rules: "Como a IA vai desenvolver, qual será o fluxo dela? Testes, validação, desenvolvimento, commit, abrir pull request, quais regras seguir etc."
- Testing: "Como pedir para IA testar a aplicação, quais casos de teste, quais cenários, quais ferramentas usar, etc."
- Debugging: "Como pedir para IA debugar a aplicação, quais ferramentas usar, quais cenários, etc."
- Refactoring
- Análise de performance
- Commit & Pull Request

### Code Review

- Análise de Discrepâncias: "Identificar e analisar discrepâncias entre o código proposto e as melhores práticas, padrões de codificação ou requisitos do projeto."
- Verificação das features implementadas
- Testabilidade e cobertura de testes
- Verificaçõa de bugs
- Documentação e comentários internos
- Coding Standards: "Padronizar como o código é desenvolvido, nome de variáveis, classes, organização, etc."

## Prompts Comumentes utilizados

### Tipos de Prompts

De acordo com a necessidade, o tipo de prompt pode variar, pois impacta diretamente na qualidade da resposta. Alguns tipos comuns incluem:

#### **Zero-shot**

"**_Fornecer uma tarefa sem exemplos_**, confiando na capacidade da IA de generalizar a partir do conhecimento prévio."

##### Quando utilizar:

- tarefas simples e conhecidas pelo modelo
- Não há tempo ou espaço para adicionar exemplos
- Deseja-se testar a capacidade base do modelo de interpretação
- É preciso processar uma grande quantidade de tarefas distintas breves e com baixo custo de tokens

##### Vantagens:

- Baixo custo
- Alta escalabilidade
- Rápida para experimentação

##### Limitações:

- Pode falhar em tarefas complexas ou com pouca familiaridade
- Sem controle sobre o formato da resposta
- Depende da compreensão do modelo sobre a tarefa
- Alucionações
- Variações na formatação da resposta
- Dificuldade em tarefas de raciocínio lógico, analises comparativas ou inferências fora do contexto

##### Estratégias de mitigação:

- **Especificidade**: "Analise esse código" > "Explique o que esse código Go faz e liste possíveis problemas de performance"
- **Linguagem declarativa orientada a tarefa**: define o que vai fazer - "Liste os principais motivos para errors de memória em GO"

- **Sinalização do formato esperado**: "Liste os princpais motivos para errors de memória em GO, em formato de lista numerada"

- **In-Context Instruction Learning**: "Você é especilista em Go", Especificar a saída desejada, Informar o seu objetivo.

#### **One-shot/few-shot**

"Fornecer um exemplo específico ou um pequeno número de exemplos (1-5) para orientar a resposta da IA, ajudando"

##### Quandok utilizar:

- A tarefa tem múltiplas formas de execução válidas e deseja orientar o estila da resposta
- modelo comete erros ou se comporta de forma inconsistente com o zero-shot
- tarefa complexa ou específica e se beneficia de demonstrações
- Necessário replicar padrões linguisticos, técnicos ou formais

#### Vantagens:

- Precisão aumentada
- Consistencia de estilo
- Pouco custo de engenharia

#### Limitações:

- Custo de tokens
- Depende da qualidade dos exemplos
- Fragilidade a ordem dos exemplos

#### Exemplo:

"Gere testes unitários para a função abaixo, seguindo o formato do exemplo fornecido:

```ts
// Exemplo de teste unitário em typescript
function add(a: number, b: number): number {
  return a + b;
}
```

```ts
// Teste unitário para a função add
import { add } from './add';
describe('add', () => {
  it('deve retornar a soma de dois números positivos', () => {
    expect(add(2, 3)).toBe(5);
  });

  it('deve retornar a soma de um número positivo e um negativo', () => {
    expect(add(5, -2)).toBe(3);
  });

  it('deve retornar a soma de dois números negativos', () => {
    expect(add(-4, -6)).toBe(-10);
  });
});
```

#### **Chain-of-Thought (CoT)**

"Pedir para a IA pensar passo a passo antes de responder, facilitando o raciocínio complexo."

##### Quando utilizar:

#### **Skeleton of Thought (SoT)**

"Fornecer um esqueleto de pensamento, onde a IA preenche os detalhes, ajudando a estruturar a resposta."

##### Quando utilizar:

#### **Tree of Thoughts (ToT)**

"Pedir para a IA explorar múltiplas possibilidades de pensamento, criando uma árvore de decisões e escolhendo o melhor caminho."

##### Quando utilizar:

#### **Self-Consistency (SC)**

"Gerar múltiplas respostas e escolher a mais consistente, aumentando a confiabilidade da resposta."

##### Quando utilizar:

#### **Directional Stimulus (DS)**

"Fornecer estímulos direcionais para guiar a resposta da IA, ajudando a focar em aspectos específicos do problema."

##### Quando utilizar:

#### **ReActing**

"Combinar raciocínio e ação, permitindo que a IA execute ações com base em seu raciocínio, como acessar ferramentas ou buscar informações adicionais."

##### Quando utilizar:
