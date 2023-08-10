# 002 - Usar gRPC para serviços críticos

Título: Serviços críticos devem permitir comunicação via protocolo gRPC

Status: Aceito

Data: 2023-08-10

## Contexto

Um sistema de pedágio (de qualidade) tem como fator crítico que a comunicação entre a praça de pedágio e a nuvem deve ser o mais rápida e leve possível.

Em especial, na faixa "sem-parar" os limites de operação e performance são muito estritos.

As tags de veículos para sistemas de pedágio usam a tecnologia RFId.

RFId (Radio Frequency Identification) é uma tecnologia de hardware que permite a sistemas IoT identificarem dispositivos, ou equipamentos que contenham as tags, a distâncias curtas (alguns metros). 

A faixa de pedágio "sem-parar" deve permitir que os veículos transitem em velocidade lenta o suficiente para que as tags RFID sejam reconhecidas, mas rápido o suficiente para que os motoristas não se sintam bloqueados.

Além disso a decisão entre abrir ou não a cancela deve fornecer tempo hábil ao motorista para fazer qualquer intervenção sem sustos evitando acidentes.

## Decisão

Vamos usar protocolo gRPC para serviços críticos entre a praça de pedágio e a nuvem.

## Razões

O protocolo [gRPC](https://grpc.io) é um protocolo binário de comunicação entre serviços que permite a transferência de dados de forma eficiente e rápida.

Outros protocolos de comunicação, ainda que sejam rápidas e úteis, não atingem uma latência mínima necessária para uma operação crítica.

Fatores como serialização, retry, circuit-break e outros, nativos do gRPC, favorecem a sua utilização em detrimento de JSON ou XML sobre HTTP, por exemplo.

## Consequências / Implicações

Definição de um seviço gRPC para comunicação entre praça de pedágio e nuvem, para decidir se abre ou não a cancela.

É necessário que o serviço já funcione sobre uma camada HTTP/2 para que o grpc possa ser usado adequadamente.

A complexidade natural de uso do gRPC força que devemos projetar um sistema bem simples para evitar atrasos no TTM (time to market).

