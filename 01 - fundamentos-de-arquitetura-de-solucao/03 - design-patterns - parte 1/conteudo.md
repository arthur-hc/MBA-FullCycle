# Design Patterns

Soluções comuns para diversos tipos de problemas

## N tier e N layered architecture

Arquitetura baseada em camadas (Presentation <=> Application <=> Data). São independentes e possuem permissões diferentes. Uma pode ser aberta a rede enquanto outra não.

## Multi-tenant architecture

Permite "múltiplos inquilinos", ou seja, uma mesma aplicação para diversos usuários. Exemplo 2 empresas compartilham o mesmo sistema, mas cada um vez apenas os seus dados de acordo com o seu tenant. É possível separa-los por banco, tabelas ou até mesmo for alguma flag (PK) no banco

## Stateless VS Stateful

O **Stateful** armazena dados da sessão no servidor, isso significa que ele cria limitações para escalar, pois dados da sessão não são replicados. Dessa forma os dados não estarão disponíveis para todos os pods. **SÃO APLICAÇÕES QUE ARMAZENAM ESTADO**

Já aplicação **Stateless** não vincula dados da sessão no servidor. Dessa forma, qualquer instância terá acesso as mesmas informações. Isso pode ser feito através de JWT, por exemplo, que são válidos em qualquer instância. Outra possibilidade caso seja necessário trabalhar com sessão seria através de um Redis, onde todas as intâncias tem acesso.

## Serverless

Seria o conceito de cloud pelo pague pelo uso, ou seja, o servidor só roda conforme a demanda. Functions são utilizadas para isso, mas não se resume a isso. O conceito é ter serviços que recebam a demanda, executem e pausem. ATENÇÃO, o conceito é muito mais amplo, isso significa que não há preocupação com o dimensionamento de infra, deployment de infra e pagamento de algo que não está sendo utilizado. Isso incluí desde S3, Lambda Function, Banco etc.

## Microsserviços

Serviços com responsabilidades específicas.

Uma das maiores vantagens seriam equipes multidisciplinares. Em equipes grandes, conflitos de versionamento, deploys impactando em outras partes diferentes, são evitadas através dessa arquitetura. Em contrapartida, pode aumentar a complexidade além de ocasionar dependencias de um serviço do outro. Por isso, recomenda-se bancos separados, para evitar impactos um no outro, além de trabalho assíncrono através de mensageria.

Outras vantagens:

- Escalabilidade de forma independente
- Separação de responsabilidades
- Diferentes tecnologia
- Baixo acoplamento

Requisitos para trabalhar:

- Maturidade da organização
- Maturidade dos times
- Deployment (Podem ter múltiplos por ter diversos problemas)
- Observabilidade é essencial
- Troubleshooting (como saber a real causa do problema)

## CQRS (Command Query Responsability Segregation)

Cria-se uma camada/área da aplicação **Command Stack** onde ocorrem mudanças no estado de algum domínio da aplicaçao (criar usuário, atualizar campo etc), mutações nos dados, não retorna dado. Nessa parte, a camada de regra de negócio pode ser contemplada

A outra área **Query Stack**, parte onde ocorrem apenas consultas e de forma simples, regras de negócio devem ser evitadas. A ideia é retornar os dados da forma mais rápida possível

De forma complementar, é possível separar o banco em 2, um para escrita e outro para leitura inclusive considerando bancos diferentes para atender a necessidade

## Caching

Sistema apartadado para acessar rapidamente os dados

## Estratégias de invalidação do cache

### Time-based invalidation

Tempo é especificado para invalidar o cache. "Daqui 5 horas esse cache será apagado", mas não se limita a TTL (mais conhecido). Pode ser algo quando o dia muda, por exemplo, ou com outras definições de tempo.

### Least Recently Used (LRU)

Remove os dados mais antigos do cache para substituir pelos novos

### Most Recently Used (MRU)

Remove os dados mais atuais do cache para substituir pelos novos. Normalmente quando só há uma versão daquele item

### Least Frequently Used (LFU)

Remove os registros que tem menos acesso

### TTL-based invalidation

Tempo específico para invalidar um cache, exemplo, daqui 5 segundos

### Write-through invalidation

Se houver atualização no disco, o cache também será atualizado. Funciona bem com sistemas que não possuem um alto índice de escrita

### Write-back invalidation

Salva no cache antes do banco de dados e quando o cache for expirar, salva no banco de dados quando for expirar. Faz sentido quando há muitas atualizações no dado

## Distributed Locking

Auxilia nos cenários de concorrência em sistemas escaláveis. Por exemplo, em um sistema de compra, onde duas pessoas tentam comprar um item com estoque 1. O lock distribuído caso duas pessoas estejam realizando a operação, trava uma. Essa abordagem traz:

- Consistência dos dados
- Contenção de recursos (torna mais eficiente)
- Evita dead locks: por exemplo, quando duas pessoas querem alterar um mesmo dado, há um lock no banco, se forem relacionados com update em cascada, um dará lock no outro, ou seja, dead lock
- Maior eficiência

### Ferramentas para implementar

- Apache Zookeeper => garante consistência, mas não é rápido
- ETCD
- Redis => Rápido, mas o tempo de replicação demora, o que pode causar dados desatualizado
- Consul
