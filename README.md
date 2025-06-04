Bem-vindo à **Consulta de Crédito - API** (apiCredito), uma aplicação fullstack projetada para a consulta e gerenciamento de operações de crédito. Este projeto integra um backend robusto desenvolvido com Spring Boot e um frontend responsivo criado com Angular, ambos containerizados com Docker para um deployment simplificado.

🔗 **Repositório:** [https://github.com/adesdsilva/apiCredito](https://github.com/adesdsilva/apiCredito)

---

## 📋 Visão Geral

Esta aplicação fornece uma solução completa para consulta de créditos constituídos, oferecendo:

*   **Backend (Spring Boot):** Uma API RESTful segura e eficiente para buscar informações de créditos por número de NFS-e ou número do crédito.
*   **Frontend (Angular):** Uma interface de usuário moderna e responsiva para interagir com a API e visualizar os dados.
*   **Banco de Dados (PostgreSQL):** Persistência dos dados de crédito.
*   **Containerização (Docker):** Orquestração simplificada dos serviços (API, Frontend, Banco de Dados) usando Docker Compose, com dados pré-carregados para facilitar o teste.

---

## ✨ Funcionalidades Principais

*   ✅ API RESTful para consulta de créditos por NFS-e e número do crédito.
*   🛡️ Tratamento robusto de exceções no backend.
*   🧪 Testes unitários na camada de controle do backend (com H2).
*   📱 Frontend responsivo compatível com desktops e dispositivos móveis.
*   🐳 Deployment fácil e rápido com Docker Compose.
*   🐘 Banco de dados PostgreSQL inicializado com dados de exemplo.

---

## 🛠️ Tecnologias Utilizadas

*   **Backend:** <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" alt="Spring Boot"/> `Java 17+` `Spring Data JPA` `Hibernate` `Maven`
*   **Frontend:** <img src="https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white" alt="Angular"/> `Node.js (LTS)` `npm`
*   **Banco de Dados:** <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
*   **Containerização:** <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/> `Docker Compose`
*   **Testes:** `JUnit 5` `Mockito` `H2 Database`

---

## 📋 Pré-requisitos

Antes de começar, garanta que você tenha as seguintes ferramentas instaladas:

| Ferramenta       | Versão Recomendada | Descrição                       |
| :--------------- | :----------------- | :------------------------------ |
| Docker           | Última estável     | Para contêineres e Docker Compose |
| Docker Compose   | Última estável     | Para orquestração de contêineres |
| Node.js          | LTS (ex: 18.x)     | Para desenvolvimento do frontend  |
| npm              | Incluído com Node.js | Gerenciador de pacotes frontend |
| Maven            | 3.8+               | Para build do backend           |
| Java             | 17 (ou compatível) | Para execução do Spring Boot    |

---

## 🚀 Iniciando com Docker (Recomendado)

A forma mais simples de executar a aplicação completa é usando Docker Compose.

1.  **Clonar o Repositório:**
    ```bash
    git clone https://github.com/adesdsilva/apiCredito.git
    cd apiCredito
    ```

2.  **Construir e Iniciar os Contêineres:**
    O `docker-compose.yml` configura os serviços: `postgres` (Banco de Dados), `api` (Backend) e `frontend` (Angular).
    ```bash
    docker-compose build
    docker-compose up -d
    ```
    *   Aguarde alguns instantes para que os serviços iniciem.
    *   O banco de dados será inicializado com dados de exemplo.

3.  **Acessar a Aplicação:**
    *   **API Backend:** Disponível em `http://localhost:8080`
    *   **Frontend:** Disponível em `http://localhost:4200`

4.  **Parar e Remover Contêineres:**
    ```bash
    docker-compose down
    ```
    *(Use `docker-compose down -v` para remover também o volume do banco de dados)*

---

## 🌐 Endpoints da API

Você pode testar a API diretamente usando `curl` ou uma ferramenta como Postman:

*   **Obter Créditos por Número da NFS-e:**
    *   URL: `GET http://localhost:8080/api/creditos/{numeroNfse}`
    *   Exemplo:
        ```bash
        curl http://localhost:8080/api/creditos/7891011
        ```

*   **Obter Detalhes de um Crédito Específico:**
    *   URL: `GET http://localhost:8080/api/creditos/credito/{numeroCredito}`
    *   Exemplo:
        ```bash
        curl http://localhost:8080/api/creditos/credito/123456
        ```

---

## 💻 Desenvolvimento Local (Opcional)

Se preferir executar os componentes separadamente sem Docker:

**Backend (Spring Boot):**

1.  Navegue até o diretório `backend`.
2.  Configure as variáveis de ambiente ou o `application.properties` para conectar a uma instância local do PostgreSQL.
3.  Construa com Maven: `mvn clean install`
4.  Execute a aplicação: `mvn spring-boot:run`

**Frontend (Angular):**

1.  Navegue até o diretório `frontend`.
2.  Instale as dependências: `npm install`
3.  Inicie o servidor de desenvolvimento: `ng serve`
4.  Acesse em `http://localhost:4200`.

---

## 🧪 Testes

*   **Backend:** Os testes unitários da camada de controle utilizam H2 como banco em memória.
    ```bash
    cd backend
    mvn test
    ```
*   **Frontend:** Atualmente, não há testes automatizados implementados para o frontend.

---

## 📂 Estrutura do Projeto

```
apiCredito/
├── backend/          # Aplicação Spring Boot (API)
│   ├── src/
│   └── pom.xml
├── frontend/         # Aplicação Angular (UI)
│   ├── src/
│   └── package.json
├── docker-compose.yml # Orquestração dos contêineres
└── README.md          # Este arquivo
```

---

## ℹ️ Detalhes Adicionais

*   **Backend:** Utiliza Spring Boot 3.x (ou versão compatível), Maven para build, e inclui tratamento de exceções customizado.
*   **Frontend:** Desenvolvido com Angular (versão estável recente), otimizado para responsividade.
*   **Docker:** A configuração garante que o banco de dados seja populado com dados iniciais ao iniciar os contêineres.

---

Desenvolvido por [adesdsilva](https://github.com/adesdsilva) ✨
