# PulseVet Backend

Backend do sistema PulseVet - API REST construída com Node.js, Express.js e Prisma ORM.

## 🚀 Tecnologias

- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **TypeScript** - Linguagem tipada
- **Prisma ORM** - ORM moderno para banco de dados
- **PostgreSQL** - Banco de dados (produção)
- **SQLite** - Banco de dados (desenvolvimento)
- **JWT** - Autenticação
- **Bcrypt** - Hash de senhas
- **Zod** - Validação de dados

## 📁 Estrutura do Projeto

```
backend/
├── src/
│   ├── controllers/     # Controladores da API
│   ├── services/        # Lógica de negócio
│   ├── middleware/      # Middlewares
│   ├── routes/          # Definição das rotas
│   ├── types/           # Tipos TypeScript
│   └── server.ts        # Servidor principal
├── prisma/
│   ├── schema.prisma    # Schema do banco
│   ├── migrations/      # Migrações
│   └── seed.ts          # Dados iniciais
└── dist/                # Código compilado
```

## 🛠️ Instalação e Configuração

### Pré-requisitos
- Node.js 18+
- PostgreSQL (produção) ou SQLite (desenvolvimento)

### Passos

1. **Instalar dependências:**
```bash
npm install
```

2. **Configurar variáveis de ambiente:**
```bash
cp .env.example .env
# Edite o arquivo .env com suas configurações
```

3. **Configurar banco de dados:**
```bash
# Gerar cliente Prisma
npm run db:generate

# Executar migrações
npm run db:migrate

# Popular banco com dados iniciais (opcional)
npm run db:seed
```

4. **Iniciar servidor de desenvolvimento:**
```bash
npm run dev
```

O servidor estará rodando em `http://localhost:3333`

## 📚 Scripts Disponíveis

- `npm run dev` - Inicia servidor em modo desenvolvimento
- `npm run build` - Compila TypeScript para JavaScript
- `npm start` - Inicia servidor em produção
- `npm run db:migrate` - Executa migrações do banco
- `npm run db:generate` - Gera cliente Prisma
- `npm run db:studio` - Abre Prisma Studio
- `npm run db:seed` - Popula banco com dados iniciais
- `npm run db:reset` - Reseta banco de dados

## 🔐 Autenticação

O sistema utiliza JWT (JSON Web Tokens) para autenticação:

- **Access Token**: Válido por 15 minutos
- **Refresh Token**: Válido por 7 dias
- **Middleware de autenticação**: Protege rotas privadas

### Endpoints de Autenticação

```
POST /api/auth/login     # Login do usuário
POST /api/auth/refresh   # Renovar access token
POST /api/auth/logout    # Logout do usuário
```

## 📋 API Endpoints

### Tutores
```
GET    /api/tutores      # Listar tutores
POST   /api/tutores      # Criar tutor
GET    /api/tutores/:id  # Buscar tutor por ID
PUT    /api/tutores/:id  # Atualizar tutor
DELETE /api/tutores/:id  # Deletar tutor
```

### Pets
```
GET    /api/pets         # Listar pets
POST   /api/pets         # Criar pet
GET    /api/pets/:id     # Buscar pet por ID
PUT    /api/pets/:id     # Atualizar pet
DELETE /api/pets/:id     # Deletar pet
```

### Agendamentos
```
GET    /api/agendamentos      # Listar agendamentos
POST   /api/agendamentos      # Criar agendamento
GET    /api/agendamentos/:id  # Buscar agendamento por ID
PUT    /api/agendamentos/:id  # Atualizar agendamento
DELETE /api/agendamentos/:id  # Deletar agendamento
```

### Consultas
```
GET    /api/consultas         # Listar consultas
POST   /api/consultas         # Criar consulta
GET    /api/consultas/:id     # Buscar consulta por ID
PUT    /api/consultas/:id     # Atualizar consulta
```

### Produtos (Estoque)
```
GET    /api/produtos          # Listar produtos
POST   /api/produtos          # Criar produto
GET    /api/produtos/:id      # Buscar produto por ID
PUT    /api/produtos/:id      # Atualizar produto
DELETE /api/produtos/:id      # Deletar produto
```

## 🗄️ Banco de Dados

### Modelos Principais

- **User**: Usuários do sistema (veterinários, atendentes)
- **Tutor**: Donos dos animais
- **Pet**: Animais de estimação
- **Agendamento**: Consultas agendadas
- **Consulta**: Registros de atendimento
- **Produto**: Itens do estoque
- **MovimentacaoEstoque**: Controle de entrada/saída

### Relacionamentos

- Tutor → Pets (1:N)
- Pet → Agendamentos (1:N)
- Pet → Consultas (1:N)
- Agendamento → Consulta (1:1)
- User → Consultas (1:N)
- Produto → MovimentacaoEstoque (1:N)

## 🔒 Segurança

- **Autenticação JWT** com refresh tokens
- **Hash de senhas** com bcrypt
- **Validação de dados** com Zod
- **CORS** configurado
- **Middleware de autenticação** para rotas protegidas

## 🚀 Deploy

### Produção (Render)

1. **Configurar variáveis de ambiente no Render**
2. **Build automático** via GitHub
3. **Banco PostgreSQL** configurado

### Comandos de Build
```bash
npm run build
npm run db:generate
npm run db:migrate
```

## 📝 Logs e Monitoramento

- Logs estruturados no console
- Tratamento de erros centralizado
- Middleware de log de requisições

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT.