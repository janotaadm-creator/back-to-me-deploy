# Back to Me Landing Page — Deploy Ready para Railway

## Status
✅ Repositório: https://github.com/janotaadm-creator/back-to-me-deploy  
✅ Branch: master  
✅ Últimos commits:
- `95c386a`: Deploy config — add Express server + Railway JSON
- `dc857ca`: (anterior)

## Estrutura Implantada
```
back-to-me-deploy/
├── public/                    # Landing page HTML/CSS/JS estático
│   └── index.html             # 27.5 KB, responsivo, ready
├── package.json               # ✅ Node dependencies
├── server.js                  # ✅ Express server serving public/
├── railway.json               # ✅ Railway deploy config (nixpacks)
├── .gitignore                 # Node + env ignores
└── README.md
```

## O que cada arquivo faz
- **server.js**: Inicia um servidor Express em `PORT` (default 3000), serve pasta `public/` como estático, fallback para `index.html` em todas as rotas
- **package.json**: Apenas dependência `express@^4.18.2`, script `npm start`
- **railway.json**: Diz ao Railway para usar `nixpacks` builder, rodar `npm start`

## Deploy no Railway — Próximos Passos

### Via webui (mais simples)
1. Acesse https://railway.app (logar com conta Senlux se preciso)
2. Novo projeto → "Deploy from GitHub"
3. Selecionar repositório `janotaadm-creator/back-to-me-deploy`
4. Railway detecta automaticamente `railway.json` e `package.json`
5. Deploy acontece; URL será gerada: `https://back-to-me-[project-id].railway.app`
6. Conectar ao backend API em `https://api-production-4996.up.railway.app` via JS no `index.html` (endpoint de checkout Stripe)

### Via CLI (requer token Railway)
```bash
cd /root/.openclaw/workspace-icaro/back-to-me-deploy
railway login  # Login com conta Senlux
railway init   # Criar novo projeto
railway up     # Deploy
```

## Próximo Passo
Após deploy no Railway (URL viva), testar:
1. Carregar https://back-to-me-[project-id].railway.app
2. Ver a landing page renderizando (hero, pricing, etc)
3. Clicar em "Teste 7 dias grátis" → validar que a chamada a `/checkout` rota para o backend API
4. Testar fluxo de checkout Stripe sandbox (se credenciais live não forem ativadas)

## Credenciais/Config Necessários (já no Railway Backend)
- **API Backend**: https://api-production-4996.up.railway.app
  - PostgreSQL privado (90 cards de teste)
  - Stripe webhooks rodando (sandbox)
  - Cadastro/login funcional
  
- **Frontend**: Precisa de `REACT_APP_API_BASE_URL` ou JS fetch() apontando para API (já no index.html)

## Arquivo de Referência (Landing Page)
/root/.openclaw/workspace-icaro/back-to-me-deploy/public/index.html (27.5 KB)
- Responsivo
- Cores: vinho, champagne, laranja, verde
- Pricing: $9, $19, $39 (placeholder para valores)
- Botão "Teste 7 dias grátis" → fetch a `/checkout`

---
**Autor**: Ícaro (subagente VPS)  
**Data**: 2026-10-21  
**Commit**: 95c386a
