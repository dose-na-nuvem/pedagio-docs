# Documento de Requerimentos de Produto - Product Requirements Document (PRD)

A **Plataforma de Cobrança Automática de Pedágio**, posteriormente denonimada *projeto* será descrita abaixo.

Esse documento descreve o projeto, em termos de negócio e mostra de forma simplificada como isso leva aos aspectos técnicos descritos mais profundamente através de documentos ASR e ADR.

# 1. Introducão à Plataforma de Cobrança Automática de Pedágio

A platforma de pedágio automático é como um filhote de baleia, pois já nasce grande.

O pedário é nativamente multi-localizado, já que funcionará em várias centrais de pedágio em regiões diversas.

Para ter sucesso no mercado, a companhia de Pedágio precisa oferecer um serviço rápido e altamente disponível, incluindo interação com sistemas externos (Sistemas de pagamento).

O nosso pedágio conta somente com a faixa de transito "sem-parar".
Não é escopo do projeto fazer funcionalidades para a faixa de pedágio "manual".

A Central de pedágio faz a detecção de tags RFId nos veículos e deve liberar a cancela da faixa "sem-parar". Essa decisão é feita através de comunicação da central de pedágio com a plataforma, na nuvem.

Para melhorar a experiência do usuário, pode-se definir como critério de operação que, mesmo que haja uma falha imediata no pagamento, em algum ponto do fluxo, a cancela seja liberada.

# 2. Escope e Objetivo

O objetivo deste projeto é proporcionar oportunidade à comunidade brasileira aprendizado e aprofundamento no desenvolvimento de aplicações nativas para nuvem, mediante apresentação técnicas, ferramentas, processos e discussões diversas.

Não é escopo desse projeto:
- desenvolver um produto real de mercado
- desenvolver integrações com sistemas externos
- desenvolver software embarcado

# 3. Stakeholders / Pessoas interessadas

Os interessados desse projeto são todos engenheiros de software (já com alguma experiência) que possam se interessar em algum dos temas desenvolvidos no projeto.

# 4. Usuários do sistema

Há diversos tipos de usuários da plataforma, mas nosso foco ficará em:

- Motoristas, que serão representados pelas tags nos seus carros
- SRE, que monitorarão a plataforma
- Desenvolvedores, que implementarão a plataforma

# 5. Requerimentos Funcionais

Há diversos requerimentos necessários para operação da plataforma, entretanto limitando-nos aos escopos e objetivos, entendemos que será necessário:

- cadastro de donos de carros e suas formas de pagamento
  - não há necessidade operacional de listagem dos mesmos
- cadastro de tags e relacionamento com donos de carros
  - não há necessidade operacional de listagem dos mesmos
- detecção de tags (simulada)
- pagamentos (simulado)
- observabilidade
  - pedágio e volume de tráfego
    - rastreamento de veículos passando pelo pedágio
    - volume de veículos
    - monitoração do SLO/SLA da operação de liberação da catraca
  - nuvem
    - qtde de pagamentos que são completados na 1a vez vs aqueles que precisam ser encadeados

# 6. Requerimentos Não-Funcionais

Securança e Privacidade:

- garantir que a comunicação entre a central do pedágio seja encriptada
- garantir que a comunicação entre a nuvem e as central de pagamento sejam encriptadas
- evitar salvar informações desnecessárias para evitar incorrer em problemas com leis
  e.g.: placa ou modelo de veículo, nome ou documento de motorista, etc.

Performance e Escalabilidade:

- atender volumes sazonais ou das horas de pico sem prejuízo ao SLO

Disponibilidade, Qualidade e Resiliência de operação:

- a plataforma deve ter alta disponibilidade pois é usada 24h/dia.
- caso haja indisponibilidade, deve ser o mínimo possível para evitar bloqueio nas estradas e não prejudicar o SLA, incorrendo em "multas".
  - como é um projeto didático, as multas podem ser trabalhadas como oportunidade para verificação do processo, criação de blameless post-mortens, revisão dos sinais de observabilidade capturados, etc.

# 7. Restrições e Premissas

O projeto será desenvolvido contando com a contribuição da comunidade, sendo em contra-partida, mentorada pelo idealizador do projeto: [Juraci Paixão](https://www.linkedin.com/in/jpkroehling/).

Não há um orçamento para o projeto e por isso, buscaremos sempre soluções gratuitas e livres de custos recorrentes ou isolados.
Inicialmente, não há prazos fixos delimitados em vista da característica exploratória do projeto, entretanto, tarefas específicas serão ajustadas para evitar devaneios ou direcionamentos fora do escopo.

# 8. Riscos e estratégias de mitigação

O sucesso desse projeto **depende exclusivamente do envolvimento da comunidade**.
Essas contribuições podem ser a nível de código, documentação, ferramentas, processos,  discussões e apresentações.

Pretende-se fazer reuniões semanais para avaliar as direções e fazer as devidas correções de planos e propósitos.

# 9. Roadmap

Ainda não há um roadmap para os componentes do projeto.

# 10. Glossary

- ADR: Arquitectural Decision Record. Documento que detalha porque uma decisão arquitetural foi tomada. [Links de apoio](https://github.com/dose-na-nuvem/pedagio-docs/issues/1#issuecomment-1671899036)
- ASR: Arquitetural Significant Requirement. Documento que detalha aspectos arquiteturais significativos relativos ou importantes de um produto, que guiam certas decisões de como o mesmo será implementado. [ASR - Wikipedia](https://en.wikipedia.org/wiki/Architecturally_significant_requirements)
- Praça ou central de Pedágio: unidade física que controla a passagem de veículos em uma via controlada.
- RFId: tecnologia que envolve software e hardware, que permite a identificação de um dispositivo por meio de antenas para radio-frequencia a distâncias curtas (na faixa de alguns metros). [RFID Wikipedia](https://en.wikipedia.org/wiki/Radio-frequency_identification)
- SLO: Service Level Objective, define os níveis de operação dos serviços internamente para que os desenvolvedores se preocupem com o que será desenvolvido.
- SLA: Service Level Agreement, acordo entre clientes e plataforma que define os níveis de operação dos serviços.



