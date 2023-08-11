# Diagramas

Este repositório contém os diagramas do projeto Dose na Nuvem os diagramas são desenvolvidos na linguagem [PlantUML](https://plantuml.com/).

## Sobre PlantUML

PlantUML é uma ferramenta que permite a geração de diagramas UML a partir de código. 

## Sobre C4-PlantUML

C4-PlantUML é uma extensão da linguagem PlantUML que facilita a criação de diagramas C4. 

## Como usar este repositório

### Passo 1: Configurar o Ambiente

Certifique-se de ter o [Docker e Docker Compose](https://docs.docker.com/engine/install/ubuntu/) instalados em sua máquina.

Coloque seus arquivos PlantUML (com extensão .puml) no mesmo diretório do arquivo Makefile e o docker-compose.yml.

### Passo 2: Usando o Makefile para Renderizar as Imagens

O Makefile possui um comando chamada "sync" que renderiza as imagens PlantUML. 

Execute o seguinte comando:

```bash
make sync
```

> Isso executará o comando Docker para renderizar as imagens dos seus arquivos PlantUML.

### Passo 3: Usando o Docker Compose para Subir o PlantUML Server

Execute o seguinte comando para iniciar o PlantUML Server usando o Docker Compose:

```bash
docker-compose up -d
```

> Isso iniciará o serviço PlantUML Server em segundo plano.

Abra um navegador web e acesse http://localhost:5052.

## Referências

- [Site oficial do PlantUML](https://plantuml.com/)
- [Repositório C4-PlantUML no GitHub](https://github.com/plantuml-stdlib/C4-PlantUML)
