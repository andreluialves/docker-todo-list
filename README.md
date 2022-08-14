# Docker Todo List

## Sobre
Projeto desenvolvido durante o módulo de Back-end do curso de desenvolvimento web da Trybe.

Foi fornecida uma aplicação full stack (um 'to do list') desenvolvida pela [Trybe](https://www.betrybe.com/) com os módulos de front-end, back-end e uma aplicação que testa a comunicação entre estes módulos.

Esta aplicação precisava ser conteinerizada para funcionar e o objetivo deste projeto foi desenvolver os arquivos de configuração para cada frente específica: Front-end, Back-end, assim como para o aplicativo de teste.

Para isso, tive que criar as imagens, configurando-as com o docker-compose, utilizando uma série de comandos do docker com diferentes níveis de complexidade.

Os arquivos principais do projeto estão na pasta `docker`, nela estão contidos:
1. Pasta `docker-commands`: onde estão os comandos exigidos pelos requisitos do projeto (resposta de cada requisito);
2. Pasta `todo-app`: onde fica a **pseudo-aplicação** desenvolvida pela Trybe, que serve como base para os `Dockerfile`s e `Compose`;

Cada comando CLI do Docker foi escrito em seu respectivo arquivo, por exemplo:
~~~
Requisito 1: ./docker/docker-commands/command01.dc
Requisito 2: ./docker/docker-commands/command02.dc
Requisito 3: ./docker/docker-commands/command03.dc
~~~

### *Status do projeto*
Este projeto encontra-se finalizado.


## Habilidades desenvolvidas
* Usar comandos Docker na CLI
* Criação e execução de contêineres Docker
* Conteinerização de aplicações
* Criar uma conexão entre conteiners
* Criação e configuração de imagens com o `docker-compose`

## Tecnologias utilizadas
* Docker
* Docker Compose
* Dockerfile


## Executando a aplicação

### 1. Clone o repositório
```
git clone git@github.com:andreluialves/docker-todo-list.git
```

  * Entre na pasta do repositório que você acabou de clonar:
```
cd docker-todo-list
```

### 2. Instale as dependências:
```
npm install
```
* Entre na pasta dos arquivos principais do projeto:
```
cd docker
```

### 3. Faça o build das imagens de back-end, front-end e testes da aplicação Todo List:

```
docker image build -t todobackend ./todo-app/back-end
docker image build -t todofrontend ./todo-app/front-end
docker image build -t todotests ./todo-app/tests
```

### 4. Suba e orquestre os containers:
```
docker-compose up -d
```

* Para rodar os teste de funcionamenmto da aplicação Todo List:
```
docker attach docker_todotests_1
```

### 5. Para abrir a visualização no navegador

   * Basta acessar a seguinte url:
```
http://localhost:3000
```
