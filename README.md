# API de Gerenciamento de Usuários

Esta API permite gerenciar usuários, possibilitando a criação, leitura, atualização e exclusão (CRUD) de dados como email, nome e idade dos usuários. A aplicação é construída usando Express e Prisma ORM.

## Funcionalidades

- **Criar Usuário**: Adicionar um novo usuário com email, nome e idade.
- **Listar Usuários**: Listar todos os usuários ou filtrar por nome, email ou idade.
- **Atualizar Usuário**: Atualizar as informações de um usuário existente.
- **Deletar Usuário**: Remover um usuário do sistema.

## Instalação

### Pré-requisitos

- **Node.js**: Certifique-se de ter o Node.js instalado (versão >= 14.x).
- **Banco de Dados**: Configure o Prisma para conectar-se ao banco de dados desejado (ex: PostgreSQL, MySQL, SQLite, etc.).

### Passos para Instalação

```bash
1. Clone o repositório para o seu ambiente local:
   git clone https://github.com/seu-usuario/seu-repositorio.git

2. Acesse a pasta do projeto:
   cd seu-repositorio

3. Instale as dependências do projeto:
   npm install

4. Configure o Prisma e conecte ao seu banco de dados:
   - Altere o arquivo `.env` com as informações de conexão do banco de dados.
   - Execute a migração para criar as tabelas no banco:
     npx prisma migrate dev --name init

5. Inicie o servidor:
   npm start
```

O servidor estará rodando em `http://localhost:3000`.

## Endpoints

### 1. Criar Usuário

**POST /usuarios**

Cria um novo usuário no banco de dados.

```json
{
  "email": "usuario@exemplo.com",
  "name": "Usuário Exemplo",
  "age": 30
}
```

**Exemplo de Resposta**:

```json
{
  "email": "usuario@exemplo.com",
  "name": "Usuário Exemplo",
  "age": 30
}
```

---

### 2. Listar Usuários

**GET /usuarios**

Lista todos os usuários ou filtra usuários com base nos parâmetros de consulta (name, email ou age).

```http
GET /usuarios?name=Usuário Exemplo
```

**Exemplo de Resposta**:

```json
[
  {
    "email": "usuario@exemplo.com",
    "name": "Usuário Exemplo",
    "age": 30
  }
]
```

---

### 3. Atualizar Usuário

**PUT /usuarios/:id**

Atualiza as informações de um usuário baseado no ID.

```json
{
  "email": "novoemail@exemplo.com",
  "name": "Usuário Atualizado",
  "age": 31
}
```

**Exemplo de Resposta**:

```json
{
  "email": "novoemail@exemplo.com",
  "name": "Usuário Atualizado",
  "age": 31
}
```

---

### 4. Deletar Usuário

**DELETE /usuarios/:id**

Deleta um usuário com base no ID.

**Exemplo de Resposta**:

```json
{
  "message": "Usuário deletado com Sucesso!"
}
```

## Tecnologias Utilizadas

- **Node.js**: Plataforma de execução JavaScript.
- **Express**: Framework web para Node.js.
- **Prisma ORM**: Gerenciamento de banco de dados e consultas.

## Como Contribuir

```bash
1. Faça um fork do projeto.
2. Crie uma nova branch: git checkout -b minha-nova-feature.
3. Faça suas alterações e adicione os commits: git commit -m 'Minha nova feature'.
4. Faça o push para a branch: git push origin minha-nova-feature.
5. Envie um Pull Request.
```

---
