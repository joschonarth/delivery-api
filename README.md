# 🚚 Delivery API

Bem-vindo à **Delivery API**, uma solução robusta para gerenciar entregas, usuários e seus respectivos logs. Esta API foi projetada com foco em escalabilidade, segurança e facilidade de integração, utilizando tecnologias modernas como Node.js, TypeScript e PostgreSQL. Ela oferece endpoints para criar e gerenciar usuários, autenticar sessões, registrar entregas e monitorar seus logs, garantindo uma experiência eficiente para o gerenciamento de serviços de entrega.

---

## 🛠️ Tecnologias Utilizadas

- **🟢 Node.js**: Ambiente de execução JavaScript para backend.
- **🟦 TypeScript**: Superset do JavaScript que adiciona tipagem estática.
- **🐘 PostgreSQL**: Banco de dados relacional.
- **🐳 Docker**: Containerização para ambientes consistentes.
- **⚡ Express**: Framework minimalista para criação de APIs.
- **🛢️ Prisma**: ORM moderno para interação com bancos de dados.
- **💎 Zod**: Validação de schemas de dados.
- **🔐 JWT (JSON Web Token)**: Autenticação e controle de acesso.
- **🧪 Jest**: Framework de testes para JavaScript.

---

## ⚙️ Funcionalidades

### 👤 Usuários 
- **➕ Criar Usuário**: Permite registrar novos usuários.

### 🔑 Sessions 
- **🛠️ Criar Sessão**: Autentica usuários e gera tokens de acesso.

### 📦 Entregas 
- **➕ Criar Entrega**: Permite cadastrar uma nova entrega.
- **📋 Mostrar Entregas**: Lista todas as entregas registradas.
- **🔄 Atualizar Status da Entrega**: Modifica o status de uma entrega existente.

### 📜 Logs de Entregas 
- **➕ Criar Log**: Adiciona um novo log associado a uma entrega.
- **📋 Mostrar Logs**: Lista os logs de uma entrega específica.

---

## ✅ Pré-requisitos

Antes de começar, você precisará ter os seguintes itens instalados na sua máquina:

- 🟢 **Node.js**: [Clique aqui para instalar o Node.js](https://nodejs.org/)
- 🐳 **Docker**: [Clique aqui para instalar o Docker](https://www.docker.com/get-started)
- 📦 **Docker Compose**: [Clique aqui para instalar o Docker Compose](https://docs.docker.com/compose/install/)

---

## 🚀 Como Executar o Projeto

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
DATABASE_URL="postgresql://<username>:<password>@localhost:5432/delivery-api?schema=public"

JWT_SECRET=<your_secret_key>
```

**5. Suba o ambiente Docker:**

```bash
docker-compose up -d
```

**6. Execute as migrações do banco de dados:**

```bash
npx prisma migrate dev
```

**7. Inicie a aplicação:**

```bash
npm run dev
```

---

## 🌐 Deploy

A **Delivery API** está disponível online e pode ser testada diretamente na produção. Caso queira testar a aplicação, você pode interagir com os endpoints utilizando a URL abaixo.

👉 Você pode testar a **Delivery API** ao acessar a URL de produção: [https://delivery-api-s8bp.onrender.com](https://delivery-api-s8bp.onrender.com)

Para testar, utilize ferramentas como **Postman** ou **Insomnia** para fazer requisições para os endpoints descritos na seção de **Endpoints**.

---

## 🔗 Endpoints

### 👤 Usuários (`/users`)
- ➕ **POST `/users`**: Criar um novo usuário.
  - Body:
    ```json
    {
      "name": "joschonarth",
      "email": "joschonarth@gmail.com",
      "password": "123456"
    }
    ```

### 🔑 Sessions (`/sessions`)
- 🔑 **POST `/sessions`**: Criar uma nova sessão (autenticação).
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

### 📦 Entregas (`/deliveries`)
- ➕ **POST `/deliveries`**: Criar uma nova entrega.
  - Body:
    ```json
    {
      "user_id": "1162ebb5-cc24-4681-a317-94dbe4853c84",
      "description": "Monitor 4K"
    }
    ```
- 📋 **GET `/deliveries`** : Listar todas as entregas.

- 🔄 **PATCH `/deliveries/:id`**: Atualizar o status de uma entrega.
  - Body:
    ```json
    {
      "status": "shipped"
    }
    ```

### 📜 Logs de Entregas (`/delivery-logs`)
- ➕ **POST `/delivery-logs`**: Criar um novo log para uma entrega.
  - Body:
    ```json
    {
      "delivery_id": "2e2acfe1-4814-4c55-bf8d-c257c7223739",
      "description": "Arrived at Distribution Center"
    }
    ```
- 📋 **GET `/delivery-logs/:delivery_id`**: Listar os logs de uma entrega específica.

---

## ✅ Testes

Este projeto utiliza o **Jest** para garantir a confiabilidade e o funcionamento correto dos recursos implementados. Para executar os testes, utilize o seguinte comando:  

```bash
npm run test:dev
```

---

## 📚 Documentações e Links Úteis

- 🟢 **Node.js**: [Documentação oficial do Node.js](https://nodejs.org/docs/latest/api/)
- 🟦 **TypeScript**: [Documentação oficial do TypeScript](https://www.typescriptlang.org/docs/)
- 🐘 **PostgreSQL**: [Documentação oficial do PostgreSQL](https://www.postgresql.org/docs/)
- 🐳 **Docker**: [Documentação oficial do Docker](https://docs.docker.com/)
- 📦 **Docker Compose**: [Documentação oficial do Docker Compose](https://docs.docker.com/compose/)
- ⚡ **Express**: [Documentação oficial do Express](https://expressjs.com/)
- 🛢️ **Prisma**: [Documentação oficial do Prisma](https://www.prisma.io/docs)
- 💎 **Zod**: [Documentação oficial do Zod](https://zod.dev/)
- 🔐 **JWT**: [Documentação oficial do JSON Web Token](https://jwt.io/introduction/)
- 🧪 **Jest**: [Documentação oficial do Jest](https://jestjs.io/docs/getting-started)

---

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

## 📞 Contato 

<div>
    <a href="https://www.linkedin.com/in/joschonarth/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
    <a href="mailto:joschonarth@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</div>