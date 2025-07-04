# PulseVet System - Sistema de Gestão Veterinária

## 🐾 Sobre o Projeto

O PulseVet System é uma **plataforma SaaS completa** para gestão de clínicas veterinárias, desenvolvida com tecnologias modernas e foco na experiência do usuário.

## 🚀 Tecnologias Utilizadas

### Frontend
- **React 18** com TypeScript
- **Vite** para build e desenvolvimento
- **Tailwind CSS** para estilização
- **Shadcn/ui** para componentes
- **React Query** para gerenciamento de estado
- **React Hook Form** com Zod para validação
- **React Router** para navegação

### Backend
- **Node.js** com TypeScript
- **Express.js** para API REST
- **Prisma ORM** para banco de dados
- **SQLite** (desenvolvimento) / **PostgreSQL** (produção)
- **JWT** para autenticação
- **Bcrypt** para hash de senhas

## 📋 Funcionalidades

### ✅ Implementadas
- Sistema de autenticação com JWT
- CRUD completo de Tutores
- CRUD completo de Pets
- Sistema de agendamentos
- Prontuário eletrônico
- Gestão de estoque
- Dashboard com métricas
- Sistema de faturas

### 🔄 Em Desenvolvimento
- Portal do cliente
- Relatórios avançados
- Notificações automáticas

## 🏗️ Arquitetura

```
vet-system-frontend-blitz/
├── src/                 # Frontend React
│   ├── components/      # Componentes reutilizáveis
│   ├── pages/          # Páginas da aplicação
│   ├── services/       # Serviços de API
│   ├── types/          # Tipos TypeScript
│   └── schemas/        # Schemas de validação
├── backend/            # Backend Node.js
│   ├── src/
│   │   ├── controllers/ # Controladores da API
│   │   ├── services/    # Lógica de negócio
│   │   ├── models/      # Modelos Prisma
│   │   └── routes/      # Rotas da API
│   └── prisma/         # Schema e migrações
└── step-by-step/       # Documentação do desenvolvimento
```

## 🚀 Como Executar

### Pré-requisitos
- Node.js 18+
- npm ou yarn
- Git

### Instalação

```bash
# Clone o repositório
git clone https://github.com/bugijo/pulsevet-system.git
cd pulsevet-system

# Instale as dependências do frontend
npm install

# Instale as dependências do backend
cd backend
npm install

# Configure o banco de dados
npx prisma migrate dev
npx prisma generate

# Execute o seed (dados iniciais)
npx prisma db seed
```

### Executando o Projeto

```bash
# Terminal 1 - Backend (porta 3333)
cd backend
npm run dev

# Terminal 2 - Frontend (porta 3000)
npm run dev
```

## 📊 Status do Desenvolvimento

- **Versão Atual:** 1.0
- **Status:** Produção
- **Cobertura de Testes:** Em desenvolvimento
- **Deploy:** Render (Backend) + Vercel (Frontend)

## 🎯 Roadmap

### V1.0 - MVP ✅
- [x] Sistema de autenticação
- [x] Gestão de tutores e pets
- [x] Sistema de agendamentos
- [x] Prontuário eletrônico
- [x] Gestão de estoque
- [x] Dashboard básico

### V2.0 - SaaS Multi-Tenant 🔄
- [ ] Arquitetura multi-tenant
- [ ] Portal do cliente
- [ ] Sites customizáveis
- [ ] Sistema de assinaturas
- [ ] Relatórios avançados

### V3.0 - IA e Automação 🚀
- [ ] Co-piloto de gestão
- [ ] Co-piloto clínico
- [ ] Análise preditiva
- [ ] Automações inteligentes

## 🤝 Contribuição

Contribuições são bem-vindas! Por favor, leia as diretrizes de contribuição antes de submeter um PR.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 📞 Contato

- **Desenvolvedor:** VetSystem Team
- **Email:** contato@pulsevet.com
- **Website:** [pulsevet.com](https://pulsevet.com)

---

**PulseVet System** - Transformando a gestão veterinária com tecnologia de ponta 🐾