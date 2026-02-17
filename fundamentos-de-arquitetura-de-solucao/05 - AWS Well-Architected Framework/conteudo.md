# AWS Well-Architected Framework

## Arquitetura de solução para Cloud

Atualmente há arquitetos especilizados em uma cloud específica

## AWS Well-Architected

Independente do provedor, há boas práticas de cloud para se seguir que podem ser seguidas mesmo no On-Premises.

Framework de boa arquitetura que pode ser utilizados em diversos provedores (mesmo não sendo AWS)

- Excelência Opercioanl
- Segurança
- Confiabilidade
- Efienciência e performance
- Otimização de custos
- Sustentabilidade

### Excelência operacional

Capacidade de oferecer suporte ao desenvolvimento e executar cargas de trabalho com eficiência. Foca no dia a dia do desenvolvimento.

#### Princípios

- **_Execute operações como como código (IaC)_**. Ao invés se configurar na interface da cloud provider, execute e suba o serviço através de comandos, apenas. Terraform auxilia nisso
- **_Faça mudanças frequentes, pequenas e reversíveis._** O erro custma menos
- **_Refine os processos de operações com frequência_**
- **_Antecipe falhas_**. É essêncial pensar em falhas, carga-los etc. Sempre pensar em um plano B
- **_Aprenda com as falhas._** Investigue, entenda e pensa em formas de não acontecer mais.

### Segurança

Indica como aproveitar as tecnologias de nuvem para segurança.

#### Princípios

- **_Implemente uma base de identity forte_**. Tenha permissões bem definidas, evite excesso de privilégios, acúmulo de permissões etc.
- **_Rastreabilidade_** é essencial para idenficar como a falha aconteceu.
- **_Ative todos os layers de segurança_** - todas as opções de segurança devem estar ativos
- **_Proteja os dados em trânsito e os armazenados_**
- **_Mantenha pessoas longes dos dados_**
- **_Prepare-se para eventos de segurança_**

### Confiabilidade

Capacidade de executar uma carga de trabalho de forma consistente independente do cenário.

#### Princípios

- **_Recupere-se automaticamente de falhas_** - capacidade de se recuperar sem a necessidade de intervenção humana

- **_Teste procedimentos de recuperação_**. consigo começar um novo banco do zero? é capaz de recriar um banco do zero?

- **_Escale horizontalmente para aumentar a disponbilidade de carga de trabalho agregada_**

- **_Pare de adivinhar capacidade_**. Teste, avalie, entenda as necessidades, não chute.

- **_Gerencie a mudança de forma automatizada_** - as alterações devem ser de forma automatica, exemplo um HPA

### Eficiência e Performance

Capacidade de utilizar recursos de computação com performance. Render mais gastando menos.

#### Princípios

- **_Democratizar tecnologias_** - compartilhar conhecimentos auxilia no crescimento da organização como um todo

- **_Torne-se global em minutos _** - atualmente é possível tornar a aplicação disponivel no mundo todo

- **_Use arquitetura serverless_** - utilizar recursos que não é mais necessário pensar na operação, utiliza, escala e paga pelo uso

- **_ Experimente com mais frequência _** - é essencial experimentar para entender as novas tecnologias

- **_Consider mechanical sympathy_** - Além de experimentar, é necessário se acostumar a utilizar aquele tipo de solução. Utilizar a ferramenta certa para o trabalho certo

### Otimização de custos

Capacidade de executar sistemas com o preço mais baixo possível de acordo com o benefício retornado

#### Princípios

- **_Implemente o Cloud Finance Management_** - Dashboards que indicam os custos, centro de custos

- **_Adote um modelo de consumo_** - Entenda o serviço e razões de adotar um modelo

- **_Meça a eficiência geral_** - Entenda o retorno para saber se a escolha faz sentido

- **_Não gaste em trabalhos que não geram diferenciais competitivos_** - O projeto gera retorno?

- **_Analise e atribua despesas_**

### Sustentabilidade

Busque eficiência, sempre. Maximizar a carga de trabalho com o menor gasto de recursos, sempre.

#### Princípios

- **_Entenda seu impacto_** - Entenda sua utilização de cloud

- **_Crie metas_** - Busque reduzir seu impacto

- **_Maximizar a utilização_** - Entenda as necessidades para saber quando escalar, por exemplo

- **_Antecipe e adote novas ofertas de hardware e software mais eficientes_** - Fique atento a novas soluções que possam impactar de forma positiva o sistema

- **_Use serviços gerenciados_** - Utilizar serviços gerenciados faz com que haja uma busca por eficiência indiretamente, contudo, há um custo por delegar o gerenciamento, cabe a empresa analisar a melhor opção.

### Principios Gerais

- Pare de adivinhar necessidades
- Sistema de teste em escala de produção
- Automatize a experimentação arquitetônica - é essencial para "motivar" testes contínuos
- Permita arquiteturas evolutivas - evite engessar
- Guie sua arquitetura usando dados - números que enfatizam cada decisão
- Melhorar duante os dias de jogo - entenda a dinâmica, as regras e forma de melhorar os processos

## Azure Well-Architected

- Desgin for self healing
- Deixe redudancias (mais confiabilidade e anti falha)
- Minimize a coordenação (menos necessidade de intervenção)
- Desenhe para esclar
- Particionamento (separe centros de custos)
- Design for operations
- Use serviços gerenciados
- Use o melhor data storage para o melhor trabalho
- Design for evolution

## 3 Níveis da arquitetura de solução

- Focada no Negócio (nível 0)
- Focada na área técnica (nível 1)
- Focada no deployment (nível 2)
