# Design Patterns Parte 2

## Configurations

Forma alternativa ao .env onde as variáveis são definidas através de um endpoint e armazenadas no Application/configuration

## Secret Management

- Evita senhas "Voando"
- Rotaciona credenciais

Serviços que auxiliam:

- Hashicorp Vault
- AWS Secret Manager

## Circuit breaker

Similar a um disjuntor.

Evita gargalos em cascata, prejudicando um serviço que já está ruim e outro que depende dele.

Imagine a seguinte situação, microsserviço 1 chama o 2, mas o 2 não está saúdavel e demora para responder para o 1 que está fora. As requisições do 1 vão chegando e tornando o 2 cada vez mais lento, demorando cada vez mais para responder o 1, que passa a ficar lento por consequência

Nessa situação, o Circuit breaker já pausaria a conexão, dando connection refused

### Estados

**Closed**: estado normal, requisições passam e sistema monitora. Requisições sao enviadas ao serviço externo, erros e timeouts contados, caso ultrapasse o limite, estado muda para Open

**Open**: estado de proteção, requisições não são feitas, retorno de erro imediato

**Half-Open**: serviços funcionam de forma parcial, ou seja, algumas requisições serão aceitas, outras não, até a normalização

Opções para solução:

- **Proxy (mais recomendado)** no MS 2: assim que percebe que o MS 2 está com problemas, esse proxy atua e já responde com erro

- **Validação no aplicação** no MS 1: ao verificar que determinada aplicação não responde, para os request durante um período

## Sequencing

Serviço (micro) para evitar gerar ids repetidos. Feito para cenários de altas exigência

## API Gateway

- Centraliza requisições
- Roteia
- Consegue trabalhar como forma de autenticação. Passou dele está ok, evitando cada microsserviço autenticar
- Converte dados (pode transformar SOAP-xml para JSON, por exemplo), insere (pode inserir id da req, por exemplo) etc
- Throttling, segura requisições para evitar gargalos nos microsserviços
- Rate Limit, pode definir n requisições/segundo, definir grupos de prioridade etc

## Event Driven Architecture (EDA)

Eventos acontecem no passado, eles são publicados em um mensage broker e um cosumidor irá consumí-los. Os tipos de eventos são:

- Event Notification - Algo Aconteceu no sistema, algo simples, atualização de status etc. Depois de acontecer, não tem relevância e é descartado
- Event Carried State Transfer - Traz os dados completos do evento, informações detalhadas que devem ser guardadas para serem utilizadas no futuro
- Event Sourcing - Grava tudo o que acontece, todas as mudanças de estado, dessa forma, permite refazer todo o reprocessamento desde o dia 1. Cria a redundância que permite recuperar informações observando a linha do tempo

Um Evento emitido, pode ser gatilho de entrada para outro sistemas

### Tipos de fila Coregrafia x Orquestação:

- **Coregrafia**: eventos ocorrem de forma independente
- **Orquestação**: há um orquestrador por traz dos eventos capaz de dar "rollback" na ordem necessária

## Pubsub - Publish Subscribe

Tipo de sistema EDA

- **Tópico/Canal** - Local recebe (consumers) e publica (publishers) informação. É centralizado e múltiplos serviços escutam o mesmo lugar, onde uma messagem é capaz de triggerar diferentes serviços de forma simultânea

## BFF - Backend for fronted

Criação de um backend específico que traz dados para um determinado tipo de cliente. Evita consumo de dados excessivos no mobile, por exemplo.

## Sidecars applications

Aplicações auxiliares na aplicação principal. Por exemplo:

- Coleta de logs
- mTLS - 2 serviços se comunicam entre sí através de seus sidecars, através de uma autenticação mTLS, garantindo segurança entre os dados
- Controle de tráfego - bloqueia o acesso

Dessa forma permita que a aplicação se concentre no "Core", funções auxiliares ficam para o sidecars

## Service Mesh

Camada de infra dedicada que você pode adicionar as aplicações através de um sidecars, por exemplo.

### Service Mesh - Istio

- Gerencia tráfego - permite serviço A ter acesso ao serviço B, ou não. Permite política de bloqueio de acesso a internet, retentativa
- Segurança
- Policy enforcement
- Oservabilidade
- Extensibilidade

Os serviços só se comunicarão através de proxy. MS A não chama direto o MS B, MS A > Proxy (Envoy) A > Proxy (Envoy) B > MS B
