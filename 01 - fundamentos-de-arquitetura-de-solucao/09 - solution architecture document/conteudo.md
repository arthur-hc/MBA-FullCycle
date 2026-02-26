# SAD (Solution Architecture Document)

Prova que garante a empresa diante do esperado do cliente. Irá atender uma gama de stakeholders, desde o responsável de produto, cliente, board etc e descreve uma arquitetura de solução.

---

Trata:

- Componentes (RabbitMQ, Kafka)
- Módulos (checkout, api gateway, admin service etc)
- Interfaces (o que é esperado)
- Fluxo de dados

---

Leva em consideração o contexto do projeto e é feito na fase de planejamento

Pontos relevantes:

- Nem todo SAD possi a mesma estrutura
- Documenta o que realmente importa
- Quanto maior o risco do projeto, maior documentação

## Tópicos tratados no documento

### Introdução

- Propósito do documento (qual a finalidade do projeto)
- Escopo da solução (o que ele deve conseguir fazer)
- Restrições (limitações, por exemplo, por que escolher uma línguagem, às vezes a escolha pode ser devido ao conhecimento do time)
- Pressupostos (quais as condições atuais, time mercado, tecnologias, acordos etc)

### Visão geral da arquitetura

- Quais os principais pontos do projeto (banco de dados, gateways, pontos técnicos críticos)
- Diagrama de alto nível
- Principais componentes (como eles se relacionam)
- Diagramas de fluxo (qual será o fluxo da aplicação)

### Requisitos funcionais e não funcionais

#### Funcionais

- Recursos
- Funcionalidades
- Features que agregam valor ao negócio
- Quais são as principais regras
- Recursos que a aplicação terá

#### Não funcionais

- Performance
- Escalabilidade
- Segurança
- Disponbilidade + cross-cutting

### Design da arquitetura

- Diagramas detalhados com sua descrição (mostrará o que é mais importante, os componentes se comunicando e o que realmente importa)
- Tecnologia utilizadas (Linguagem, tipo de banco, cloud provider e o racional das decisões)
- Detalhamente das integrações (como os sistemas se comunicam)
- Detalhamento maior em um nível mais baixo que nos tópicos anteriores

### Implementação

- Quais metodologias de desenvolvimento e ferramentas no momento do desenvolvimento
- Processos de deployment e infraestrutura
- Processos de teste e qualidade

### Operação e gestão de mudanças

- Monitoramento (o que monitorar? métricas? volumetria?)
- Processos de manutenção (qual o horário por exemplo?)
- Disaster recovery (como lidará em momentos de desastre? Se o banco ficar fora por exemplo?)
- Processos de gerenciamento de mudanças

### Riscos e estratégias de mitigação

- Mapeamento dos riscos potenciais
- Riscos de grande impacto
- Estretégias de mitagação em falhas proprias ou de terceiros
- Plano de contigência (o que fazer em caso de falha?)

### Custos, tecnologia e pessoal

- Estimativa de custos para implementação
- Recomendação de equipes e pessoal

### Próximos passos

- Sugestão de ordem de execução
- Observações gerais
