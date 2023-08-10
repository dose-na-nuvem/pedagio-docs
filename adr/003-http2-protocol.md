# 003 - Usar HTTP2 para serviços não críticos

Título: Usar protocolo HTTP/2 para serviços simples e permitir upgrade para gRPC quando necessário

Status: Aceito

Data: 2023-08-10

## Contexto

Uma plataforma de pedágio conta com diversos serviços "simples", crud, pagamento, integração de APIs, que precisam se comunicar, e majoritariamente, eles usarão a tecnologia mais estável existente no mercado.

Outros sistemas críticos da plataforma que usam gRPC também necessitam das bases de HTTP/2 (como upgrade de conexão) para funcionarem adequadamente.

## Decisão

Vamos usar o protocolo HTTP/2 para serviços gerais, exceto naqueles que tiverem restrições.

## Razões

O protocolo HTTP/2 é um protocolo de rede, evolução do HTTP/1 que é atualmente o padrão para quaisquer aplicações nativas em nuvem.

O HTTP/2 disponibiliza a fundação para uma conexão de longa vida, em tempo real, para comunicação de multiplos fluxos.

## Consequências / Implicações

Usar o protocolo HTTP/2 facilitará que desenvolvedores possam integrar os serviços desenvolvidos em diversas plataformas pré-existentes.

