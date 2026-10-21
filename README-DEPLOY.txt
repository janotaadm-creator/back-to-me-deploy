# 🚀 Back to Me Landing — Deploy Railway — Ready to Ship

## ✅ ENTREGÁVEIS

| Item | Status | Local |
|------|--------|-------|
| Landing Page (HTML/CSS/JS) | ✅ Pronto | `/public/index.html` (27.5 KB) |
| Node/Express Server | ✅ Testado | `server.js` |
| Railway Config | ✅ Pronto | `railway.json` |
| npm Dependencies | ✅ Instalado | `package.json` |
| GitHub Repo | ✅ Atualizado | https://github.com/janotaadm-creator/back-to-me-deploy |
| Documentação Deploy | ✅ Completa | `DEPLOY-READY.md` |

## 🔗 Próximo Passo (5 min)

### Para Guilherme: Deploy via Railway webui
1. Abrir https://railway.app
2. **Sign in** com GitHub (janotaadm-creator ou senlux-gl)
3. **New Project** → **Deploy from GitHub**
4. Selecionar: `janotaadm-creator/back-to-me-deploy`
5. Clicar **Deploy**
6. Esperar build + deploy automático (~2-3 min)
7. Copiar URL: `https://back-to-me-[PROJECT_ID].railway.app`

### Ou via CLI (para VPS com token)
```bash
cd /root/.openclaw/workspace-icaro/back-to-me-deploy
railway login
railway init
railway up
```

## 📋 Testes Locais (VPS — Ícaro)
```bash
✅ npm install        # 0 vulnerabilities
✅ npm start          # Server rodando em localhost:3000
✅ GET /             # Landing HTML renderizando
✅ GET /health       # {"status":"ok","timestamp":"..."}
```

## 🎨 Landing Page (Features)
- **Hero**: "App que você abre todo dia — Teste 7 dias grátis"
- **Pricing**: $9 / $19 / $39 (placeholder)
- **Botão CTA**: "Teste 7 dias grátis" → fetch `/checkout` no backend
- **Design**: Responsivo (mobile-first), cores Senlux
- **Integração**: Conecta ao backend API em https://api-production-4996.up.railway.app

## 🔐 Backend (Já Online)
- API: https://api-production-4996.up.railway.app
- Health: ✅ 200 OK
- DB: PostgreSQL + 90 cards
- Stripe: Sandbox + webhooks

## 📦 Commits
```
d9c8f05 docs: deployment readiness guide for Railway
95c386a Deploy config: add Express server + Railway JSON for static hosting
dc857ca Add deployment configurations (Cloudflare, Vercel)
```

## 🎯 Após Deploy
1. Testar URL live
2. Clicar "Teste 7 dias grátis" → Stripe checkout
3. Validar integração backend
4. Atualizar Trello #1330 (Com você)
5. Ativar credenciais Stripe live (quando pronto para vendas)

---
**Status**: AGUARDANDO DEPLOY via Railway webui  
**Data**: 2026-10-21 22:35 UTC-3  
**Responsável**: Ícaro (VPS)  
**Próximo**: Guilherme (GitHub OAuth)
