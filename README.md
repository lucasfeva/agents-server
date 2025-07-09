# NLW Agents - Server

Um servidor backend para gerenciamento de salas usando Node.js, Fastify e PostgreSQL.

## Tecnologias Utilizadas

- Node.js - Runtime JavaScript
- Fastify - Framework web rápido e eficiente
- TypeScript - Tipagem estática para JavaScript
- Drizzle ORM - ORM type-safe para PostgreSQL
- PostgreSQL - Banco de dados relacional
- pgvector - Extensão PostgreSQL para vetores
- Zod - Validação de esquemas TypeScript
- Biome - Linter e formatter

## Estrutura do Projeto

```bash
src/
├── db/
│   ├── connection.ts     # Conexão com banco de dados
│   ├── schema/           # Schemas do banco
│   ├── migrations/       # Migrações do banco
│   └── seed.ts           # Dados de teste
├── http/
│   └── routes/           # Rotas da API
├── env.ts                # Configuração de ambiente
└── server.ts             # Servidor principal
```

## Setup e Configuração

1. **Pré-requisitos**

   - Node.js 18+
   - Docker e Docker Compose

2. **Instalação**

   ```bash
   # Instalar dependências
   npm install

   # Copiar arquivo de ambiente
   cp .env.example .env
   ```

3. **Banco de Dados**

   ```bash
   # Iniciar PostgreSQL com Docker
   docker-compose up -d

   # Executar migrações
   npx drizzle-kit migrate

   # Popular banco com dados de teste
   npm run db:seed
   ```

O servidor estará disponível em `http://localhost:3333`

## Rotas da API

- `GET /health` - Health check
- `GET /rooms` - Listar salas

## Comandos Úteis

```bash
# Gerar migrações
npx drizzle-kit generate

# Visualizar banco (Drizzle Studio)
npx drizzle-kit studio

# Executar seed
npm run db:seed
```

## Configuração de Ambiente

Variáveis necessárias no arquivo `.env`:

```bash
PORT=3333
DATABASE_URL=postgresql://root:root@localhost:5432/nlw_agents
```
