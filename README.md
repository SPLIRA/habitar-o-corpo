# ATTUAL ONE Foundation

Fundacao profissional em Next.js 15, TypeScript, Tailwind CSS, Supabase, PWA, ESLint e Prettier.

Este repositorio contem somente a base tecnica do projeto. Nao ha telas, banco, autenticacao ou funcionalidades de produto implementadas.

## Scripts

```bash
npm run dev
npm run build
npm run lint
npm run type-check
npm run format
```

## Arquitetura

- `src/app`: entrada do Next.js App Router.
- `src/components`: componentes reutilizaveis sem regra de negocio.
- `src/features`: modulos verticais de funcionalidades futuras.
- `src/lib`: clientes e adaptadores de infraestrutura.
- `src/hooks`: hooks compartilhados.
- `src/services`: servicos de aplicacao e orquestracao.
- `src/types`: contratos TypeScript globais.
- `src/styles`: estilos globais e Tailwind.
- `src/utils`: utilitarios puros e genericos.

## Ambiente

Copie `.env.example` para `.env.local` quando for configurar integrações reais.

As variaveis do Supabase estao apenas preparadas para uso futuro. Nenhum banco ou autenticacao foi criado.
