# Sistema de Agendamento para Barbearia

## Descrição do Projeto

Um software web moderno para agendamento de serviços em barbearias. Permite que clientes marquem horários de forma fácil e online, enquanto os barbeiros e administradores gerenciam a agenda, serviços e atendimentos de maneira eficiente.

**Objetivo:** Facilitar o agendamento, reduzir faltas, otimizar o tempo dos profissionais e melhorar a experiência do cliente.

## Funcionalidades Principais (MVP sugerido)

### Para Clientes (usuários finais):
- Cadastro e autenticação (email/senha ou Google)
- Visualização da lista de serviços com preços, duração e descrição
- Calendário interativo mostrando horários disponíveis
- Seleção de serviço + barbeiro (se houver mais de um)
- Confirmação de agendamento com resumo
- Área "Meus Agendamentos" para visualizar e cancelar
- Notificações (email ou futuro WhatsApp)

### Para Barbeiros / Administradores:
- Login com permissões de admin
- Dashboard com agenda do dia e da semana
- Gerenciamento de disponibilidade (bloquear horários, definir horário de trabalho)
- CRUD de serviços (adicionar, editar preços/tempos)
- Visualização de histórico de clientes e agendamentos
- Confirmação manual de presença/falta

### Funcionalidades Futuras:
- Integração com pagamento (Pix, cartão)
- Sistema de lembretes automáticos
- App mobile (React Native)
- Múltiplas barbearias (multi-tenant)
- Avaliações e feedback dos clientes
- Relatórios de faturamento

## Stack Tecnológica Recomendada

| Camada       | Tecnologia Sugerida          | Alternativa Simples       |
|--------------|------------------------------|---------------------------|
| Frontend    | Next.js + Tailwind CSS      | HTML + CSS + JS + Bootstrap |
| Backend     | Node.js + Express + Prisma  | Python Flask/FastAPI     |
| Banco       | PostgreSQL                  | SQLite / MongoDB         |
| Autenticação| NextAuth.js ou JWT + bcrypt | Firebase Auth            |
| Calendário | react-big-calendar ou FullCalendar | Calendly embed (rápido) |
| Deploy      | Vercel (frontend) + Railway/Render (backend) | Heroku / Netlify         |

## Estrutura de Pastas Sugerida (para Next.js Fullstack)

```
barbearia-agendamento/
├── app/                  # Next.js App Router
├── components/          # Componentes reutilizáveis
├── lib/                 # Prisma client, utils
├── prisma/              # Schema do banco
├── public/              # Imagens, etc.
├── types/               # TypeScript types
├── README.md
├── IDEA.md
└── package.json
```

## Como Começar (próximos passos)

1. **Clonar o repositório**:
   ```bash
   git clone https://github.com/Pedrosoares7i/barbearia-agendamento.git
   cd barbearia-agendamento
   ```

2. **Definir o escopo do MVP** juntos (o que é essencial primeiro?)

3. **Escolher a stack** definitiva (eu recomendo Next.js + Prisma + PostgreSQL para algo profissional e escalável)

4. **Criar wireframes** simples (posso te ajudar a descrever as telas)

5. **Iniciar o desenvolvimento** passo a passo

## Dúvidas para você:

- Prefere uma solução mais simples (só frontend + backend básico) ou fullstack moderna com TypeScript?
- Vai ter apenas 1 barbeiro ou vários?
- Quer começar pelo frontend ou pelo backend?
- Tem preferência por alguma tecnologia que já conhece?

Vamos construir isso juntos! Qualquer ideia ou mudança, me avise que eu ajudo a atualizar o repositório e o plano.