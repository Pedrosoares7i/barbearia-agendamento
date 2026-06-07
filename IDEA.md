# Sistema de Agendamento para Barbearia - Projeto Interdisciplinar ETEC

## Contexto do Projeto

Este sistema é o projeto interdisciplinar do **2º módulo da ETEC**. O objetivo é aplicar conhecimentos de **todas as matérias** em um sistema web completo de agendamento de serviços para barbearia.

**Restrições importantes:**
- **Não haverá integração com pagamentos** (Pix, cartão, etc.)
- **Obrigatório uso de banco de dados** (relacional recomendado)
- **Controle de acesso por papéis (roles)** bem definido

## Papéis de Usuário (Roles) e Permissões

O sistema deve ter pelo menos 3 tipos de usuário com permissões diferentes:

### 1. Cliente (Usuário comum)
- Cadastrar-se e fazer login
- Visualizar serviços disponíveis
- Agendar horário (escolher serviço + barbeiro + data/hora disponível)
- Ver apenas **seus próprios agendamentos**
- Cancelar **apenas seus próprios agendamentos** (com regras, ex: com antecedência mínima)
- **Não pode** deletar reservas de outros clientes

### 2. Barbeiro
- Login próprio
- Ver **sua própria agenda** (agendamentos do dia/semana)
- Gerenciar sua disponibilidade (bloquear horários, definir horário de expediente)
- Confirmar presença/falta do cliente (opcional no MVP)
- Ver histórico de atendimentos realizados por ele
- **Não gerencia** outros barbeiros ou clientes

### 3. Administrador (Admin)
- Acesso total ao sistema
- Gerenciar **todos os agendamentos** (ver, editar, deletar qualquer reserva)
- Gerenciar serviços (CRUD: criar, editar, excluir preços e durações)
- Gerenciar barbeiros (adicionar, editar, desativar)
- Gerenciar clientes (ver lista, desativar contas)
- Gerenciar disponibilidade geral
- Ver relatórios simples (ex: agendamentos por dia, serviços mais procurados)
- **Pode deletar qualquer reserva** (exemplo dado no seu requisito)

> **Importante para o projeto escolar:** O sistema deve validar essas permissões no backend (não só no frontend). Use sessões ou tokens + verificação de role em cada página/rota.

## Funcionalidades do MVP (Mínimo Viável)

### Funcionalidades Gerais
- Cadastro e login com controle de papéis
- Lista de serviços com preço e tempo estimado
- Calendário com slots de horário disponíveis (por barbeiro)
- Confirmação de agendamento

### Para Cliente
- Agendar
- Meus agendamentos (listar + cancelar)

### Para Barbeiro
- Minha agenda
- Gerenciar minha disponibilidade

### Para Admin
- Dashboard geral
- Gerenciar tudo (agendamentos, serviços, barbeiros, clientes)
- Deletar qualquer agendamento

## Banco de Dados (Obrigatório)

Deve ser modelado um banco de dados relacional. Sugestão de tabelas principais:

- `usuarios` (id, nome, email, senha_hash, role, telefone, data_cadastro, ativo)
- `servicos` (id, nome, preco, duracao_minutos, descricao, ativo)
- `barbeiros` (id, usuario_id, especialidade, horario_inicio, horario_fim, dias_trabalho)
- `agendamentos` (id, cliente_id, barbeiro_id, servico_id, data_hora, status, observacao)
- `disponibilidade` (id, barbeiro_id, data, hora_inicio, hora_fim, disponivel)

**Entregáveis esperados no projeto:**
- Diagrama Entidade-Relacionamento (DER)
- Script SQL de criação das tabelas
- Normalização das tabelas

## Stack Tecnológica Recomendada para ETEC (2º Módulo)

Como é projeto interdisciplinar e você está no 2º módulo, recomendo uma stack **clássica e didática**:

| Camada       | Tecnologia Recomendada          | Por quê?                                      |
|--------------|----------------------------------|--------------------------------------------------|
| Frontend    | HTML + CSS + Bootstrap + JavaScript | Fácil, visual, ensina estrutura básica     |
| Backend     | PHP (com PDO)                   | Controle de sessões, roles, lógica no servidor |
| Banco       | MySQL                           | Obrigatório no projeto + fácil de usar       |
| Autenticação| Sessões PHP + password_hash() | Ensina segurança básica                     |
| Calendário | FullCalendar.js ou simples inputs de data/hora | Visual e funcional                              |

**Alternativa mais moderna (se permitido):** Next.js + Prisma + PostgreSQL, mas pode ser mais avançado para o módulo.

**Vantagens da stack PHP + MySQL:**
- Você aprende backend de verdade
- Fácil de rodar localmente (XAMPP/WAMP)
- Combina perfeitamente com matérias de Banco de Dados e Programação Web

## Estrutura de Pastas Sugerida (PHP)

```
barbearia-agendamento/
├── assets/              # CSS, JS, imagens
├── config/              # Conexão com banco
├── controllers/         # Lógica (auth, agendamento, admin)
├── includes/            # Header, footer, auth check
├── models/              # Classes ou funções de banco
├── pages/               # Páginas (login, dashboard, agendar, etc.)
├── sql/                 # Scripts de banco de dados
├── README.md
├── IDEA.md
└── index.php
```

## Entregáveis Típicos de Projeto Interdisciplinar ETEC

- Diagrama de Casos de Uso
- Diagrama Entidade-Relacionamento (DER)
- Modelo Lógico e Físico do Banco
- Telas do sistema (prints ou protótipo)
- Código fonte organizado
- Relatório explicando como cada matéria foi aplicada
- Demonstração funcionando

## Próximos Passos

1. Confirmar a stack que você quer usar (PHP + MySQL é a mais indicada para ETEC?)
2. Modelar o banco de dados (posso te ajudar a fazer o DER)
3. Definir o fluxo completo de cada papel (telas + permissões)
4. Começar a implementar o login + controle de roles

## Dúvidas para você responder:

- Quais matérias estão envolvidas no projeto interdisciplinar? (ex: Programação, Banco de Dados, Análise de Sistemas...)
- A escola permite ou prefere PHP + MySQL, ou tem que usar outra coisa (Python, Java, etc.)?
- Quer que eu já monte o **script SQL** completo das tabelas + o Diagrama ER em texto?
- Prefere começar pelo **modelo do banco de dados** ou pelas **telas/fluxos**?
- Vai ter só 1 barbeiro ou vários?

Me responde essas perguntas que eu atualizo o IDEA.md novamente e começamos a construir o projeto de verdade (código, diagramas, etc.).

Estamos juntos nisso! Qualquer dúvida ou ideia nova, manda aqui.