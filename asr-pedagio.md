# ASR (Architectural Significant Requirements)

Status: Em revisão

Data: 2023-08-11

Esse ASR irá apontar requerimentos arquiteturais significativos extraídos a partir da definição do produto (PRD).

Os requerimentos significativos são aqueles que impactam profundamente a maneira como o sistema será desenvolvido.

Essas questões podem afetar processos, sistemas ou hardwares.

# Identificação 

Conforme descrito no [PRD](./pdr-pedagio.md), temos algumas questões **bem significativas**:

1. um sistema multi-localizado fisicamente
2. que transita informações sensíveis (pagamento e identificação de veículos)
3. necessitando alta performance de operação e comunicação entre serviços
4. requer alta disponibilidade
5. que precisa ser resilientes em horários de pico e dias específicos
6. precisa garantir conclusão de operações para evitar evasão de divisas
7. precisa de monitoração em tempo real

# Soluções

## Multi-localização

Um sistema multi-localizado é basicamente um candidado a aplicação nativa em nuvem. Além disso, a criticidade de operação é uma força que indica a necessidade de se ter pontos de presenta do software próximo às regiões de operação física.

Sugestão

- sistema distribuído em microserviços

## Comunicação segura

Como as informações transitadas entre micro-serviços podem ser sensíveis, exige-se protocolos e tecnologias rápidas e seguras

Sugestão

- uso de protocolo HTTP/2
- uso de protocolo gRPC
- uso de TLS entre micro-serviços

## Alta performance e Resiliência

A criticidade de performance na operação sugere a definição de SLO/SLA de latência, baixos o suficiente para permitir 

A alta disponibilidade para operação em momentos de alta demanda pode ser atendidos em termos de recursos disponibilizados.

Sugestão:

- multiplas cópias de serviços automaticamente escaladas em função de demanda 
  - orquestrador de serviços: kubernetes
- redundância de serviços:
  - hpa nos serviços dentro do kubernetes

## Resiliência

A a resiliência para operação em momentos de alta demanda pode ser atendidos em termos de recursos disponibilizados.

Sugestão:

- retries para operações críticas
  - gRPC, filas de eventos para reprocessamento
- enfileiramento para reprocessamento de ações diversas
  - filas, Kafka, PubSub, SNS
- fallback em requisições de rede para usar
- load balancer para controle de requisições
  - kubernetes, gRPC


# Detalhes de implementação

Poderá ser implementado no futuro.

# Razões

Poderá ser implementado no futuro.

# Trade-offs

Poderá ser implementado no futuro.

# Testes e validação

Todos os microserviços deverão ser implementados com testes.

# Lições aprendidas

Fazer o registro das lições aprendidas.

