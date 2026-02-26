# Solution Architecture

Processo para definição da estrutura, componentes, interfaces de uma solução de software para atender requisitos funcionais e não funcionais.

É necessário pensar desde as regras do negócio até como implementar sistema, como escalar, manter disponível etc.

Trata-se de uma visão mais macro, que buca montar todo um sistema integrado e capaz de atender as necessidades

## Perfil da pessoa arquiteta de solução

- **Experiência no negócio**: é essencial entender sobre o negócio para saber desenhar a melhor solução

- **Conhecimento de tecnologias**: é necessário conhecimento das ferramentas disponíveis para propor a melhor solução

- **Conhecimento do contexto**: além das capacidades anteriores, é necessário entender o contexto da empresa, pois isso pode impactar completamente a tomada de decisão, e uma mesmo problema pode ser resolvido de formas completamente diferentes em razão dos contextos

- **Preparo para entregar soluções complexas**: problemas simples não exigiram esse tipo de profissional

## Soft skills

- **Flexibilidade**: saber se adaptar aos mais diversos contextos e projetos

- **Comunicação**: por estar em contato com os mais diversos times e níveis, comunicação é essencial

- **Liderança**: a tomada de decisão é essencial, assim como saber vender a sua ideia e conduzir o processo

- **Pensamento estratégico**: conseguir pensar além, ter uma visão macro

- **Criatividade**: ter a capacidade de criar soluções inovadoras

- **Inteligência emocional**: muitas cobranças e responsabilidades

- **Trabalhar em equipe**

- **Saber ouvir**

## Princípios para arquitetar um solução

- **Alinhamento com negócio**: devemos entender o negócio, cultura, o que a empresa quer antes de desenvolver
- **Flexibilidade**: é essencial para atender cenários diversos que podem ocorrer
- **Reusabilidade**: é necessário saber reutilizar o que já foi feito, mesmo que seja difícil.
- **Interoperabilidade**: capcidade desse sistema de se comunicar com outros sistemas
- **Mantenabilidade**: deve ser fácil de dar manutenção, desde bugs até o deploy
- **Compliance**: Deve seguir as normas regulatórias locais
- **Portabilidade**: a informação deve ser de fácil acesso e migração

## Iniciando com TCO (Total Cost of Ownership)

A aplicação deve atender as necessidades do negócio e deve ser claro o seu impacto. Para isso, é necessário saber o TCO, avaliando seu custo de desenvolvimento e de manutenção da aplicação, levando em consideração cada escolha, inclusive as tecnológicas e seus impactos

Custo de:

- Aquisição
- Implementação
- Manutenção
- Operação
- Inativação

Custo de utilizar uma pronta do mercado X desenvolver

O custo da aplicação realmente traz retorno? Nem sempre a melhor solução técnica é viável ou a melhor do ponto de vista de negócio

## Enterprise Architecture X Solution Architecture

EA possuí o foco na organização como um todo, SA é focada em uma solução específica

A SA está em baixo de uma EA

## 3 Camadas da arquitetura de solução

- Arquitetura focada no negócio (nível 0)
- Arquitetura focada no técnico (nível 1)
- Arquitetura focada no deployment (nível 2)

O arquiteto de solução deve ser capaz de entender o negócio (1), como a solução deve ser desenvolvida (2) e como será sua infraestrutura (3)

## Nível 0 - Visão e Escopo

### Visão:

Traz a razão da solução e seu impacto na empresa

### Escopo:

Entendo quais são as responsabilidades da solução, até que pontos ela deve atender, definindo limites a nível de negócio, técnico e pressupostos

## Domínio e contextos:

Entendimento do negócio inclusive dos seus diferentes pontos de vista como vendedores, parceiros, diferentes departamentos etc.

## Domínios e linguagem

Ao arquitetar uma solução, deve-se considerar que um mesmo item pode ter diferentes nomes de acordo com a área, por exemplo:

- Vendedores > Ingresso
- Suporte > Ticket
- Parceiros > Ticket

É recomendado criar um glossário por stakeholders

## Lei de Conway

A estrutura organizacional influencia diretamente no design da aplicação. Decisões, forma de se organizar, comunicação entre áreas etc, tudo isso tem impacto arquitetura de uma solução

## View e Viewpoints

A impressão, pontos focais e conclusões sobre algo, varia de acordo com a realidade de cada um. Exemplo, um design irá perceber pontos diferentes de um engenheiro de software

View é uma perspectiva sobre a solução, enquanto uma viewpoint é uma **maneira** de olhar para o sistema de um ângulo específico.
