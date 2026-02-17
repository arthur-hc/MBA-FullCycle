# Observabilidade

Capacidade de demonstrar o que ocorre dentro da aplicação para alguém que não conhece a aplicação, uma caixa preta.Demonstra os dados de entrada e saída

## Observabilidade VS Monitoramento

### Monitoramento

- Monitoramento demonstra quando há algo errado
- Baseia-se em saber com antecedência quais sinais deseja monitorar
- Não mostra a causa raíz, apenas o resultado final

### Observabilidade

- A observabilidade permite entender o **porquê** do resultado final

## Pilares vs Pipes

Pipes são intersecções, dados que se misturam

- **Logs**: eventos que ocorreram no passado (sistema criado, e-mail enviado, usuário atualizado... etc)
- **Metrics**: medidas, dados que é possível agregar (Média de consumo de RAM, número de usuários simultâneos, consumo de CPU... etc)
- **Tracing**: forma de rastrear o que está acontecendo na aplicação. Request Scoped, onde é possível mapear o caminho completo da requisição, passagem em cada componente da aplicação, passagem em outras aplicações etc

O Conceito de pipe complementa a de pilares, pois pilares são conceitos separados, no entando, o conceito de pipe remete a analise agregada, onde esses pilares serão analisados em conjunto para entender um mesmo problema

## Ferramentas populares

- **Elastic Stack**
- **Datadog**
- **New Relic**
- **Splunk**
- **Dynatrace**
- **Prometheus / Grafana**
- **Jaeger**
- **Zipkin**
- **Kiali**

## OpenTelemetry (OTEL)

Um CNCF Project baseado no Open Tracing e Open Census. Segue os padrões e convenções definidas, dessa forma, permite trocar de serviços apenas no driver, pois o padrão será o mesmo

Baseado em:

- Especificações
- Protocolos
- SDKs (prontas para diversas linguagens)
- Ferramentas de integração

Possibilidades:

- App > OTel Collector/Agent > Backend (serviço de observabilidade)
- App > OTel Collector/Agent > OTel Service > Backend (serviço de observabilidade)
- App > OTel Service

Aqui é aplicado a ideia de sidecars, onde há uma micro aplicação auxiliando a aplicação

Os coletores pode se comunicar com diversos backends e de forma simultânea
