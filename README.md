# Habitar o Corpo — Joelma Souza

PWA instalável para clientes conhecerem serviços, agendarem atendimentos e acessarem uma área VIP protegida. Este é um protótipo funcional com dados locais, preparado para deploy na Vercel e futura migração para Supabase.

## Dados oficiais

- App: Habitar o Corpo
- Marca: Joelma Souza — Terapeuta Integrativa
- Frase: Habitar o corpo é voltar para si.
- Domínio planejado: app.joelmasouzaoficial.com.br
- WhatsApp: 5512988830247
- Pix provisório: 11987080279
- Endereço: Rua Fabiola Regina Sardinha, 47 - Res. Armando Moreira Righi, São José dos Campos - SP, CEP: 12247-812

## Acessos de demonstração

- Admin: `joelmaespacosama@gmail.com` / `Joelma67@#$`
- VIP: `cliente@vip.com` / `JOELMAVIP`
- Cliente demo VIP: `mariana@email.com` / `123456`
- Cliente demo comum: `renata@email.com` / `123456`

## Rodar localmente

Na pasta do projeto, rode:

```bash
python -m http.server 5173
```

Depois acesse:

```text
http://localhost:5173
```

O PWA precisa rodar por `http://localhost` ou `https` para service worker e instalação funcionarem corretamente.

## Deploy na Vercel

Opção simples:

1. Acesse `https://vercel.com/drop`.
2. Arraste a pasta do projeto para a tela.
3. Escolha o nome do projeto, por exemplo `habitar-o-corpo`.
4. Clique em deploy.

Opção com Git:

1. Crie um repositório no GitHub.
2. Envie estes arquivos para o repositório.
3. Na Vercel, clique em `Add New Project`.
4. Importe o repositório.
5. Mantenha como projeto estático, sem build command.
6. Publique.

O arquivo `vercel.json` já está pronto para servir o app como SPA/PWA.

## Configurar app.joelmasouzaoficial.com.br

1. Na Vercel, abra o projeto publicado.
2. Vá em `Settings` > `Domains`.
3. Adicione `app.joelmasouzaoficial.com.br`.
4. A Vercel mostrará o registro DNS necessário.
5. No painel DNS do domínio `joelmasouzaoficial.com.br`, crie um registro `CNAME`:
   - Nome/Host: `app`
   - Valor/Target: copie exatamente o valor indicado pela Vercel.
6. Aguarde a propagação e confirme na própria tela de Domains da Vercel.

Não altere registros de e-mail do domínio, como MX, SPF, DKIM ou DMARC.

## Instalar no Android

1. Abra `https://app.joelmasouzaoficial.com.br` no Chrome.
2. Toque no menu de três pontos.
3. Toque em `Instalar app` ou `Adicionar à tela inicial`.
4. Confirme a instalação.

## Instalar no iPhone

1. Abra `https://app.joelmasouzaoficial.com.br` no Safari.
2. Toque no botão de compartilhar.
3. Toque em `Adicionar à Tela de Início`.
4. Confirme o nome `Joelma Souza`.

## Arquivos PWA

- `manifest.json`: manifesto principal.
- `public/manifest.json`: cópia preparada para futura migração React/Vite.
- `service-worker.js`: cache básico dos assets principais.
- `icons/icon-192.png`: ícone Android.
- `icons/icon-512.png`: ícone PWA.
- `icons/icon-512-maskable.png`: ícone maskable.
- `icons/favicon.png`: favicon.
- `icons/apple-touch-icon.png`: ícone iOS.
- `vercel.json`: configuração de deploy.

## Próximos passos futuros

- Trocar fotos e vídeos de exemplo por materiais reais.
- Migrar dados locais para Supabase.
- Adicionar autenticação real.
- Migrar Minha Conta para Supabase Auth.
- Criar bucket privado para conteúdos VIP.
- Validar conflito de horários no backend.
