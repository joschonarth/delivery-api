# 🚚 Delivery API

Bem-vindo à **Delivery API**, uma solução robusta para gerenciar entregas, usuários e seus respectivos logs. Esta API foi projetada com foco em escalabilidade, segurança e facilidade de integração, utilizando tecnologias modernas como Node.js, TypeScript e PostgreSQL. Ela oferece endpoints para criar e gerenciar usuários, autenticar sessões, registrar entregas e monitorar seus logs, garantindo uma experiência eficiente para o gerenciamento de serviços de entrega.


## 🛠️ Tecnologias Utilizadas

- **🌐 Node.js**: Ambiente de execução JavaScript para backend.
- **📘 TypeScript**: Superset do JavaScript que adiciona tipagem estática.
- **⚡ Express**: Framework minimalista para criação de APIs.
- **🛢️ Prisma**: ORM moderno para interação com bancos de dados.
- **🐘 PostgreSQL**: Banco de dados relacional.
- **🐳 Docker**: Containerização para ambientes consistentes.
- **✅ Zod**: Validação de schemas de dados.
- **🔐 JWT (JSON Web Token)**: Autenticação e controle de acesso.
- **🧪 Jest**: Framework de testes para JavaScript.

---

## ⚙️ Funcionalidades

### 👤 Usuários (`/users`)
- **➕ Criar Usuário**: Endpoint para registrar novos usuários.

### 🔑 Sessions (`/sessions`)
- **🛠️ Criar Sessão**: Endpoint para autenticar usuários e gerar tokens de acesso.

### 📦 Entregas (`/deliveries`)
- **➕ Criar Entrega**: Permite cadastrar uma nova entrega.
- **📋 Mostrar Entregas**: Lista todas as entregas registradas.
- **🔄 Atualizar Status da Entrega**: Modifica o status de uma entrega existente.

### 📜 Logs de Entregas (`/delivery-logs`)
- **➕ Criar Log**: Adiciona um novo log associado a uma entrega.
- **📋 Mostrar Logs**: Lista os logs de uma entrega específica.

---

## 🗺️ Rotas

### 👤 Usuários
- **POST `/users`** ➕: Criar um novo usuário.
  - Body:
    ```json
    {
    "name": "joschonarth",
    "email": "joschonarth@gmail.com",
    "password": "123456"
    }
    ```

### 🔑 Sessions
- **POST `/sessions`** 🔑: Criar uma nova sessão (autenticação).
  - Body:
    ```json
    {
    "email": "joschonarth@gmail.com",
    "password": "123456"
    }
    ```
  - Response:
    ```json
    {
      "token": "jwt-token"
    }
    ```

### 📦 Entregas
- **POST `/deliveries`** ➕: Criar uma nova entrega.
  - Body:
    ```json
    {
    "user_id": "1162ebb5-cc24-4681-a317-94dbe4853c84",
    "description": "Monitor 4K"
    }
    ```
- **GET `/deliveries`** 📋: Listar todas as entregas.

- **PATCH `/deliveries/:id`** 🔄: Atualizar o status de uma entrega.
  - Body:
    ```json
    {
    "status": "shipped"
    }
    ```

### 📜 Logs de Entregas
- **POST `/delivery-logs`** ➕: Criar um novo log para uma entrega.
  - Body:
    ```json
    {
    "delivery_id": "2e2acfe1-4814-4c55-bf8d-c257c7223739",
    "description": "Arrived at Distribution Center"
    }
    ```
- **GET `/delivery-logs/:deliveryId`** 📋: Listar os logs de uma entrega específica.

---

## ✅ Pré-requisitos

Antes de começar, você precisará ter os seguintes itens instalados na sua máquina:

- 🟢 **Node.js**: [Clique aqui para instalar o Node.js](https://nodejs.org/)
- 📦 **npm** (gerenciador de pacotes do Node.js): O npm vem automaticamente com a instalação do Node.js.
- 🐳 **Docker**: [Clique aqui para instalar o Docker](https://www.docker.com/get-started)
- 🐳 **Docker Compose**: [Clique aqui para instalar o Docker Compose](https://docs.docker.com/compose/install/)

## 🚀 Instalação e Execução

1. Clone o repositório:

```bash
git clone https://github.com/joschonarth/delivery-api.git
```

2. Acesse o diretório do projeto:

```bash
cd delivery-api
```

3. Instale as dependências:

```bash
npm install
```

4. Configure as variáveis de ambiente no arquivo `.env` na raiz do projeto:

```plaintext
DATABASE_URL="postgresql://<user>:<password>@localhost:5432/delivery-api?schema=public"

JWT_SECRET=
```

5. Suba o ambiente Docker:

```bash
docker-compose up -d
```

6. Execute as migrações do banco de dados:

```bash
npx prisma migrate dev
```

7. Inicie a aplicação:

```bash
npm run dev
```

## ✅ Testes

Execute os testes com o Jest:

```bash
npm run test:dev
```

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

## 📞 Contato 

<div>
    <a href="https://www.linkedin.com/in/joschonarth/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
    <a href="mailto:joschonarth@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</div>