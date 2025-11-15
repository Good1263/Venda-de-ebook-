# BookHub — Projeto Completo

Este projeto é uma **loja de ebooks** com muitas features:
- Lista de ebooks + busca e filtros
- Carrinho avançado (remover, alterar quantidade, total)
- Modal de detalhes, compra "Buy now"
- Autenticação com Firebase (opcional) — fallback demo local
- Painel Admin (demo, sem backend)
- PWA básico (manifest + service worker)
- Instruções para publicar no GitHub Pages e Vercel

---

## Como usar (local)

1. Extraia o ZIP e abra `index.html` no navegador.
2. Se quiser usar autenticação real com Firebase:
   - Crie um projeto no https://console.firebase.google.com/
   - Habilite Authentication -> Email/Password
   - (Opcional) habilite Firestore para armazenar livros
   - Copie a configuração do app (SDK) e cole em `firebase-config.js` na variável `window.FIREBASE_CONFIG`
   - O arquivo `firebase-auth.js` inicializará o SDK (compat).  

> Sem configuração do Firebase você pode usar a autenticação demo (local) — NÃO USE em produção.

---

## Publicar no GitHub Pages

1. Crie um repositório público (ex: `bookhub-site`).
2. Faça push dos arquivos (`index.html`, `styles.css`, `script.js`, `manifest.json`, `sw.js`, `firebase-config.js`, `firebase-auth.js`, `README.md`, etc).
3. Vá em **Settings > Pages** e selecione branch `main` e folder `/ (root)`.
4. Aguarde e acesse `https://<seu-usuario>.github.io/<repo>`.

Observação: GitHub Pages é ótimo para sites estáticos. Se você usar Firebase (Firestore/Functions), configure regras e deploy separadamente.

---

## Deploy no Vercel

1. Crie uma conta em https://vercel.com/ e conecte seu repositório.
2. Para site estático, Vercel detecta automaticamente e faz deploy sem configuração adicional.
3. Cole suas variáveis de ambiente (se usar alguma) no painel do Vercel.
4. Vercel provê HTTPS e deploy contínuo a cada push.

---

## Integração com Pagamentos

Este projeto contém **pagamentos simulados** (PIX/cartão). Para integrar pagamentos reais:
- Sugestões: Stripe, Gerencianet, PagSeguro, MercadoPago.
- Nunca coloque chaves secretas no frontend — use um backend (Firebase Functions, Node.js, etc).

---

## Notas de segurança e melhorias

- O painel Admin é apenas uma demo local (livros são salvos no localStorage).
- Para produção, crie um backend (Firebase Firestore + Functions, ou Node/Express) e proteja rotas e credenciais.
- Adicionar imagens reais e otimização de assets (lazy-loading, compressão).
- Implementar testes automatizados, CI e revisões de segurança.

---

Se quiser, eu posso:
- Ajudar você a criar o projeto no GitHub e subir os arquivos.
- Configurar Firebase passo a passo e incluir Firestore.
- Integrar Stripe (exemplo de backend + frontend).
- Ajustar o design ainda mais ou converter para React/Vue.

Diga qual próximo passo deseja e eu guiarei você. 
