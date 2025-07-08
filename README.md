# NLW Agents Server

Servidor desenvolvido durante o evento NLW Agents da Rocketseat para gerenciamento de agentes e salas.

## 🚀 Tecnologias Utilizadas

- **Node.js** - Runtime JavaScript
- **TypeScript** - Superset do JavaScript com tipagem estática
- **Fastify** - Framework web rápido e eficiente
- **Drizzle ORM** - ORM TypeScript-first para PostgreSQL
- **PostgreSQL** - Banco de dados relacional
- **Zod** - Validação de esquemas TypeScript
- **Docker** - Containerização do banco de dados
- **Biome** - Linter e formatador de código

## 📋 Pré-requisitos

- Node.js 22+
- Docker e Docker Compose
- PostgreSQL (via Docker)

## 🛠️ Setup e Configuração

### 1. Clone o repositório

```bash
git clone <repository-url>
cd nlw-agents-server
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

```bash
cp .env.example .env
```

### 4. Execute o banco de dados

```bash
docker-compose up -d
```

### 5. Execute as migrações

```bash
npx drizzle-kit migrate
```

### 6. Execute o seed do banco (opcional)

```bash
npm run db:seed
```

### 7. Execute o servidor

```bash
# Desenvolvimento
npm run dev

# Produção
npm start
```

## 📂 Estrutura do Projeto

```
src/
├── db/
│   ├── connection.ts      # Configuração da conexão com o banco
│   ├── seed.ts           # Dados iniciais do banco
│   ├── migrations/       # Migrações do banco de dados
│   └── schema/           # Esquemas das tabelas
├── http/
│   └── routes/           # Rotas da API
├── env.ts                # Validação de variáveis de ambiente
└── server.ts             # Configuração do servidor
```

## 🔧 Scripts Disponíveis

- `npm start` - Executa o servidor em produção
- `npm run dev` - Executa o servidor em modo desenvolvimento
- `npm run db:seed` - Popula o banco com dados iniciais

## 📡 API Endpoints

- `GET /health` - Health check da aplicação
- `GET /rooms` - Lista todas as salas

## 🐳 Docker

O projeto utiliza Docker para executar o PostgreSQL com a extensão pgvector. O banco de dados é configurado automaticamente através do `docker-compose.yml`.

## 📝 Padrões de Projeto

- **Repository Pattern** - Separação da lógica de acesso a dados
- **Dependency Injection** - Inversão de controle
- **Schema Validation** - Validação de dados com Zod
- **Environment Configuration** - Configuração através de variáveis de ambiente

---

Desenvolvido durante o evento **NLW Agents** da [Rocketseat](https://rocketseat.com.br/) 🚀
