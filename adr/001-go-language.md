# 001 - Usar linguagem Go

Título: Adoção de Go como linguagem principal de desenvolvimento

Status: Aceito

Data: 2023-08-09

## Contexto

Como é um projeto novo, temos liberdade de escolher qualquer linguagem. A concisão da linguagem, o ecosistema, a experiência que o idealizador do projeto tem com a linguagem, as ferramentas e os serviços que futuramente serão parte do projeto, são todos elementos que corroboram com a decisão de implementar os microserviços em Go.

## Decisão

Nós iremos adotar a linguagem de desenvolvimento Go para construir os microserviços.

## Razões

1. **Simplicidade e legibilidade:**  Go é conhecido por sua simplicidade e concisão. É fácil de ler e escrever código e evita que os códigos fiquem complexos.

2. **Alta-performance, inter-operabilidade e escalabilidade:**  Go é compilado em código de máquina que executa nativamente em máquinas de diversos sistemas operacionais. Além disso, criar concorrência (paralelismo) em Go é muito mais simples que em outras linguagens.

3. **Comunidade:**  Go tem uma comunidade de desenvolvedores muito atuante e presente no Brasil. Há diversos recursos, bibliotecas e frameworks (em português inclusive) que podem ser usados para criar aplicações robustas.
 
4. **Flexibility:**  Embora sua presença seja mais marcante no cenário de aplicações backend, ele também pode ser usado até mesmo para criar frontend.

5. **Maturidade para Apps nativas em Nuvem:**  Go é de facto uma linguagem pensada e desenvolvida para atuar num cenário de aplicações distribuidas em núvem.

## Consequências / Implicações

1. **Treinamento:**  Os participantes que não têm conhecimento da linguagem poderão absorvê-la acompanhando as evoluções de código,trazendo discussões nos chats (telegram,discord), além de seguir com pesquisas e aprofundamento individuais sem prejuízo para acompanhamento dos assuntos tratados.

2. **Experiência:**  Alguns temas tratados podem ser bem difíceis de acompanhar, entretando seria tanto ou mais trabalhoso em outras linguagens. maio objetivo do projeto não é Go, mas permitir que as pes

3. **Ferramentas:**  Iremos adotar ferramentas especificas da linguagem. Entretanto, praticamente tudo poderá ser usado em outros sistemas operacionais com mínimo ou nenhum impacto.

4. **Vendor lock-in:**  Go é uma linguagem de código aberto e assim não ficaremos presos a nenhum fabricante ou sistema.

## Conclusão

A adoção de Go como linguagem principal de programação irá ajudar o desenvolvimento de microserviços robustos alinhados com o requerimento cloud-native do projeto.

<h6>Créditos: Esse documento foi criado com base no documento similar: https://github.com/joelparkerhenderson/architecture-decision-record/tree/main/examples/go-programming-language.</h6>