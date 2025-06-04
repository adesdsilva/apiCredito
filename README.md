apiCredito - Aplicação Fullstack com Spring Boot e Angular
Bem-vindo ao apiCredito, uma aplicação fullstack projetada para gerenciar operações de crédito. Este projeto integra um backend robusto desenvolvido com Spring Boot e um frontend responsivo criado com Angular, ambos containerizados com Docker para um deployment simplificado. A aplicação inclui um banco de dados PostgreSQL, uma API RESTful e um frontend compatível com dispositivos móveis.

📋 Visão Geral
Backend: Construído com Spring Boot, a API oferece endpoints para gerenciar operações de crédito. Inclui testes unitários na camada de controle usando o banco H2 em memória e tratamento robusto de exceções.
Frontend: Desenvolvido com Angular, o frontend é otimizado para desktops e dispositivos móveis. Pode ser servido localmente com ng serve e acessado em http://localhost:4200.
Docker: Utiliza Docker Compose para orquestrar três contêineres: PostgreSQL (banco de dados), API Spring Boot e frontend Angular, inicializados com registros pré-carregados no banco.
✨ Funcionalidades
API RESTful para gestão de créditos.
Tratamento de exceções para maior robustez.
Testes na camada de controle com banco H2.
Frontend compatível com dispositivos móveis.
Deployment containerizado com PostgreSQL, API e frontend.
📋 Pré-requisitos

Ferramenta	Versão Recomendada	Descrição
Docker	Última versão estável	Para contêineres e Docker Compose
Docker Compose	Última versão estável	Para orquestração de contêineres
Node.js	LTS (ex.: 18.x)	Para desenvolvimento do frontend
npm	Incluído com Node.js	Gerenciador de pacotes do frontend
Maven	3.8+	Para build do backend
Java	17 (ou versão compatível)	Para execução do Spring Boot
🌐 Endpoints
Teste a API usando curl com os seguintes endpoints:

Obter Crédito por ID: http://localhost:8080/api/creditos/7891011
bash

Collapse

Wrap

Run

Copy
curl http://localhost:8080/api/creditos/7891011
Obter Detalhes do Crédito: http://localhost:8080/api/creditos/credito/123456
bash

Collapse

Wrap

Run

Copy
curl http://localhost:8080/api/creditos/credito/123456
🚀 Iniciando o Projeto
1. Clonar o Repositório
bash

Collapse

Wrap

Run

Copy
git clone https://github.com/adesdsilva/apiCredito.git
cd apiCredito
2. Construir e Executar com Docker
O arquivo docker-compose.yml no repositório configura três contêineres:

postgres: Banco de dados PostgreSQL com registros pré-carregados.
api: Backend Spring Boot.
frontend: Frontend Angular.
Execute os seguintes comandos para construir e iniciar os contêineres:

bash

Collapse

Wrap

Run

Copy
docker-compose build
docker-compose up -d
A API estará disponível em http://localhost:8080.
O frontend estará disponível em http://localhost:4200 (servido pelo contêiner Angular).
3. Parar e Remover Contêineres
Para parar e remover os contêineres:

bash

Collapse

Wrap

Run

Copy
docker-compose down
4. Desenvolvimento do Backend (Opcional)
Para construir e executar o backend localmente sem Docker:

Navegue até o diretório backend:
bash

Collapse

Wrap

Run

Copy
cd backend
Construa o projeto com Maven:
bash

Collapse

Wrap

Run

Copy
mvn clean install
Execute a aplicação:
bash

Collapse

Wrap

Run

Copy
mvn spring-boot:run
5. Desenvolvimento do Frontend (Opcional)
Para desenvolver o frontend localmente sem Docker:

Navegue até o diretório frontend:
bash

Collapse

Wrap

Run

Copy
cd frontend
Instale as dependências:
bash

Collapse

Wrap

Run

Copy
npm install
Inicie o servidor de desenvolvimento:
bash

Collapse

Wrap

Run

Copy
ng serve
Acesse o frontend em http://localhost:4200.
6. Executar Testes
Testes do Backend: A API inclui testes na camada de controle com H2. Execute-os com:
bash

Collapse

Wrap

Run

Copy
cd backend
mvn test
Testes do Frontend: Não há testes de frontend implementados atualmente.
📂 Estrutura do Projeto
backend/: Contém a aplicação Spring Boot com:
Controladores REST com tratamento de exceções.
Testes unitários com banco H2.
Configuração para PostgreSQL no Docker.
frontend/: Contém a aplicação Angular com:
Design responsivo para dispositivos móveis.
Componentes para a interface de gestão de créditos.
docker-compose.yml: Define a configuração dos três contêineres (PostgreSQL, API, frontend).
ℹ️ Detalhes Adicionais
Backend
Framework: Spring Boot 3.5.0 (ou versão compatível mais recente).
Banco de Dados: PostgreSQL, inicializado com registros de exemplo.
Funcionalidades: API RESTful para operações de crédito, tratamento de exceções (ex.: classes de exceção personalizadas) e H2 para testes.
Ferramenta de Build: Maven.
Frontend
Framework: Angular (versão estável mais recente).
Compatibilidade: Otimizado para dispositivos móveis com técnicas de design responsivo (ex.: media queries CSS, flexbox).
Ferramenta de Build: npm.
Servidor de Desenvolvimento: ng serve para recarregamento automático durante o desenvolvimento.
Configuração Docker
Contêineres:
postgres: Executa o banco de dados PostgreSQL com dados pré-carregados.
api: Hospeda a aplicação Spring Boot, conectada ao PostgreSQL.
frontend: Serve a aplicação Angular, construída e servida via servidor web leve (ex.: Nginx).
Inicialização: O docker-compose.yml garante que o banco seja populado com registros iniciais ao iniciar.
