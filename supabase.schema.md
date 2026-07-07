# Migração futura para Supabase

Este protótipo usa `localStorage` para funcionar sem backend. Para produção, a estrutura pode migrar para Supabase com as tabelas abaixo.

## Tabelas

### services

- id: uuid
- slug: text
- name: text
- description: text
- duration: text
- price: text
- benefits: text[]
- active: boolean
- created_at: timestamptz

### appointments

- id: uuid
- service_id: uuid
- service_name: text
- customer_name: text
- customer_phone: text
- customer_email: text
- date: date
- time: text
- notes: text
- status: text
- created_at: timestamptz

### vip_contents

- id: uuid
- title: text
- description: text
- type: text -- text, video, image, pdf, audio, link
- url: text
- thumbnail: text
- category: text
- text_content: text
- status: text -- active, inactive
- access: text -- VIP
- created_at: timestamptz

### vip_users

- id: uuid
- name: text
- login: text
- active: boolean
- created_at: timestamptz

### clients

- id: uuid
- role: text
- is_vip: boolean
- name: text
- phone: text
- email: text
- city: text
- accepted_terms: boolean
- active: boolean
- created_at: timestamptz

### admins

- id: uuid
- email: text
- name: text
- created_at: timestamptz

## Storage

Bucket sugerido: `vip-contents`

- Acesso público: não.
- Leitura: apenas VIP autorizado ou admin.
- Escrita: apenas admin.
- No protótipo atual, conteúdos VIP são cadastrados por URL/link.
- Na migração futura, arquivos próprios devem ser enviados ao Supabase Storage e a URL assinada deve ser salva em `vip_contents.url`.

## Regras de negócio

- Cliente comum pode criar agendamento.
- Cliente autenticado pode ler e editar seu próprio cadastro.
- Cliente autenticado pode ler seus próprios agendamentos.
- Admin pode ler, editar e excluir agendamentos.
- Admin pode editar clientes, ativar/desativar VIP e remover acesso.
- Recuperação de senha atual é provisória por WhatsApp/admin manual.
- Em produção, migrar recuperação para Supabase Auth com fluxo seguro de reset por e-mail.
- Admin pode criar serviços, conteúdos VIP e usuários VIP.
- Conteúdo VIP só deve ser exibido para usuário autorizado.
- Bloqueio de horário deve ser validado no backend antes de confirmar o agendamento.
