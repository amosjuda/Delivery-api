# Delivery API

API REST para gerenciamento de entregas, com autenticação JWT, Swagger, Docker e PostgreSQL.

## Visão Geral

Este projeto é uma API RESTful desenvolvida com Spring Boot, projetada para gerenciar o fluxo de entregas entre clientes e motoristas. Ele abrange desde o cadastro de usuários e entregas até o rastreamento do status da entrega, com um foco em segurança, escalabilidade e boas práticas de desenvolvimento.

## Tecnologias Utilizadas

* **Java 17+:** A linguagem de programação base.
* **Spring Boot 3:** O framework para construção da aplicação Java.
* **Spring Web:** Para construção de aplicações web, incluindo APIs RESTful.
* **Spring Security:** Para segurança da aplicação, incluindo autenticação e autorização.
* **Spring Data JPA:** Para persistência de dados em banco de dados relacional.
* **PostgreSQL:** O banco de dados relacional utilizado.
* **Swagger/OpenAPI:** Para documentação da API.
* **Docker:** Para conteinerização da aplicação e do banco de dados.
* **JWT:** Para autenticação e autorização baseada em tokens.
* **AWS (Opcional):** Para deploy na nuvem (Elastic Beanstalk ou EC2).

## Funcionalidades

* Cadastro de clientes e motoristas.
* Solicitação de entregas (com status: pendente, a caminho, concluída).
* Autenticação: usuários com diferentes roles (admin, cliente, motorista).
* Endpoints protegidos com JWT.
* Listagem e atualização do status da entrega.
* Filtros de entrega por status, datas, cidade, etc.
* Documentação da API com Swagger.
* Implantação simplificada com Docker Compose.
* Deploy na AWS (opcional).

## Estrutura do Projeto

A estrutura de pacotes do projeto é organizada da seguinte forma:

    src/main/java/com/deliveryapi
    ├── config
    │   └── SwaggerConfig.java  # Configuração do Swagger
    ├── controller
    │   ├── AuthController.java  # Controla a autenticação
    │   └── DeliveryController.java # Controla as operações de entrega
    ├── dto
    │   ├── DeliveryDTO.java   # Transferência de dados de entrega
    │   └── UserDTO.java       # Transferência de dados de usuário
    ├── entities
    │   ├── Delivery.java    # Entidade de entrega
    │   └── User.java        # Entidade de usuário
    ├── enums
    │   └── DeliveryStatus.java # Enum para status da entrega
    ├── repository
    │   ├── DeliveryRepository.java # Repositório de entregas
    │   └── UserRepository.java     # Repositório de usuários
    ├── security
    │   ├── JwtUtil.java       # Utilitários para JWT
    │   └── SecurityConfig.java    # Configuração de segurança
    ├── service
    │   ├── DeliveryService.java  # Lógica de negócio para entregas
    │   └── UserService.java      # Lógica de negócio para usuários
    └── DeliveryApiApplication.java # Ponto de entrada da aplicação

## Como Rodar o Projeto

### Pré-requisitos

* Java 17+
* Docker

### Utilizando Docker Compose

A maneira mais fácil de rodar o projeto é utilizando o Docker Compose. Certifique-se de ter o Docker instalado e siga os passos abaixo:

1.  Clone este repositório.
2.  Navegue até o diretório do projeto.
3.  Execute o seguinte comando:

    ```bash
    docker-compose up --build
    ```

    Este comando irá construir a imagem da aplicação e do banco de dados PostgreSQL, e irá iniciá-los.
4.  A API estará disponível em `http://localhost:8080`.
5.  A documentação do Swagger estará disponível em `http://localhost:8080/swagger-ui/index.html`.

### Configuração Manual (Sem Docker)

Se você preferir rodar a aplicação sem Docker, siga os passos abaixo:

1.  Instale o PostgreSQL e crie um banco de dados chamado `delivery_db` (ou altere a configuração no arquivo `application.properties`).
2.  Configure as variáveis de ambiente necessárias (JWT secret, etc.).
3.  Utilize o seu IDE (IntelliJ, Eclipse, etc.) para importar o projeto como um projeto Maven ou Gradle.
4.  Execute a classe `DeliveryApiApplication`.
5.  A API estará disponível em `http://localhost:8080`.
6.  A documentação do Swagger estará disponível em `http://localhost:8080/swagger-ui/index.html`.

## Próximos Passos

* Implementar os controladores e serviços para as entidades `User` e `Delivery`.
* Configurar o Spring Security para autenticação e autorização com JWT.
* Criar os DTOs para transferência de dados entre a API e a aplicação.
* Implementar o tratamento de erros e validações.
* Configurar o Swagger para documentação da API.
* (Opcional) Configurar o deploy na AWS.

## Contribuição

Sinta-se à vontade para contribuir com este projeto. Se encontrar algum problema ou tiver alguma sugestão, abra uma issue ou envie um pull request.
