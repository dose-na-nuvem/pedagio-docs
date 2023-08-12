# ASR (Architectural Significant Requirements)

Status: Em revisão

Data: 2023-08-11

Esse ASR irá apontar requerimentos arquiteturais significativos extraídos a partir da definição do produto (PRD).

Os requerimentos significativos são aqueles que impactam profundamente a maneira como o sistema será desenvolvido.

Essas questões podem afetar processos, sistemas ou hardwares.

# Requerimentos

Conforme descrito no [PRD](./pdr-pedagio.md), temos algumas questões **bem significativas**:

1. um sistema multi-localizado fisicamente
2. que transita informações sensíveis (pagamento e identificação de veículos)
3. necessitando alta performance de operação e comunicação entre serviços
4. precisa ter alta disponibilidade mesmo em horários de pico e dias específicos
5. precia ter resiliência no caso de falhas internas
6. precisa garantir conclusão de operações para evitar evasão de divisas
7. precisa de monitoração em tempo real

# ASRs

## ASR 001 Multi-localização

Requerimento: o sistema deve funcionar em vários locais físicos diferentes.
Razão: O requerimento é importante pois sem isso não é possível manter o empreendimento.
Impacto arquitetural: O sistema deve ser desenvolvido através de serviços que podem ser implantados isoladamente, cumprindo funções similares mas sempre acessando uma fonte de dados.
Dependências: O sistema precisa se comunicar com um banco de dados.

## ASR 002 Banco de dados

Requerimento: os serviços do sistema deve acessar dados consistentes, independente do seu local de implantação.
Razão: Sem dados consistente, o usuário poderá ser bloqueado erroneamente ou pior, pode ser cobrado indevidamente.
Impacto arquitetural: Deve existir um banco de dado acessível a todos os serviços. Preferencialmente o banco deve ser único, pois múltiplas instâncias poderiam ocasionar em dificuldades de replicação ou sincronia.
Dependências: nenhuma

## ASR 003 Performance

**Rascunho: precisa confirmar os valores** 
Requerimento: o sistema deve liberar a passagem de veículos transitanto a 60km/h em uma faixa "sem-parar" com 100m de extensão.
Razão: os usuários não querem reduzir a velocidade pois acreditam que a tecnologia deve ser capaz de atendê-los com excelência.
Impacto arquitetural: deve ser escolher protocolos de comunicação extremamente rápidos e eficientes. Deve-se escolher linguagens de computação de alta perfomance. Se possível, permitir implantar pontos de presença próximos aos locais de operação.
Dependências: nenhuma.

## ASR 004 Comunicação segura

Requerimento: as informações transitadas entre os serviços do produto devem ser encriptadas.
Razão: Deve-se usar as melhores práticas de segurança contra o acesso indevido dos dados transitados.
Impacto arquitetural: uso de protocolo seguros na comunicação entre serviços.
Dependências: nenhuma

## ASR 005 Escalabilidade

Requerimento: o sistema deve atender os usuários com a mesma qualidade seja em horários de pico, seja em dias de feriados.
Razão: degradação do serviço nos momentos citados pode provocar transtornos aos usuários, ou mesmo, causar acidentes.
Impacto arquitetural: deve-se escolher uma arquitetura escalável, gerenciada automaticamente em função da demanda, que multiplique os módulos de sistema necessários à operação dentro dos parâmetros definidos no SLA/SLO.
Dependências: nenhuma


## ASR 006 Resiliência

Requerimento: O sistema deverá (ou poderá) liberar a passagem de veículos ainda que não consiga realizar a cobrança imediatamente.
Razão: por regulamentação Rx, os usuários não devem ser impedidos de transitar ou serem cobrados indevidamente, por falhas técnicas do sistema, exceto por acidentes na via ou desastres de causas naturais.
Impacto arquitetural: o sistema deve realizar multiplas tentativas de pagamento dentro do intervalo de trânsito do carro na via. O sistema deve enfileirar as tentativas caso extrapole o número tentativas imediatas.
Dependências: nenhuma

## ASR 007 Monitoração em tempo real

Requerimento: o sistema deverá transparecer o volume de tráfego na via para órgãos de gestão e fiscalizadores
Razão: órgãos de trânsito e outras instituições podem usar as informações para prestarem serviço de utilidade pública. A própria central pode usar essas informações para melhorar sua gestão de manutenções preventivas em determinados locais.
Impacto arquitetural: os eventos e processamentos mais importantes do sistema deverão ser instrumentados (com tecnologia padrão de mercado) para permitir coletas de métricas e indicadores de performance.
Dependências: nenhuma



## Conclusão

O sistema proposto apresenta muitas característica que o qualificam como um "projeto nativo em nuvem".

A lista de ASRs detalhou possíveis impactos arquiteturais.

Cada decisão arquitetural final deverá ser documentada via ADRs em local próprio.