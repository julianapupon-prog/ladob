# Lado B

Site-presente pra um fã de rock/synth dos anos 80 (Depeche Mode, Billy Idol). Página única, HTML/CSS/JS puro, sem build.

## Como rodar
Abrir com um servidor local (não direto pelo `file://`, por causa do áudio):

```
npx serve .
# ou
python3 -m http.server 8000
```

## O que já tem
- **Topo laranja:** um disco grande girando, que sobe quando você rola a página
- **Prateleira:** carrossel de discos em perspectiva (inspirado em a24.raviklaassens.com), com créditos e 3 faixas por álbum
- **Discos em SVG:** vinil colorido, sulcos, reflexo e selo com listras anos 70. Quando a capa real carrega, ela vira o selo
- **Música:** prévias de 30s pela iTunes Search API (JSONP, sem chave). Se a busca falhar, entra uma trilha sintetizada em Web Audio
- **Mini player fixo** embaixo da tela enquanto toca
- **Seções:** Pra você, Vitrine (Edifier e Retrôaudiolab, com links), Casarão do Vinil, 7 bares de audição (lista da CNN Brasil), Do arquivo, Agenda (artistas seguidos ficam salvos no localStorage)
- **Notificações:** toasts e o painel do sininho
- **Animações ao rolar:** aparecem conforme a seção entra na tela, via IntersectionObserver. Respeita `prefers-reduced-motion`

Fontes: Fraunces (SOFT/WONK) e Inter Tight, do Google Fonts.

## O que falta (próximos passos)
1. **Testar as prévias reais:** depois de publicado, confirmar que a busca do iTunes acha a faixa certa e que as prévias e capas carregam
2. **Deploy:** GitHub Pages, Vercel ou Netlify
3. **Alertas de preço de verdade:** precisam de backend e cron (ex.: Vercel Cron + Supabase) checando as lojas. A Edifier e a Retrôaudiolab (Wix) não têm API pública, então seria scraping, que é frágil. Pra vinil, a API do Discogs é o melhor caminho
4. **Push notifications:** Web Push com service worker. No iPhone só funciona se o site for adicionado à tela inicial
5. **Apple Music completo:** MusicKit JS (precisa de conta Apple Developer) pra tocar faixas inteiras e recomendar com base no histórico dele
6. **Notícias e shows:** RSS de sites de música. Pros shows, a lista de artistas seguidos + alguma API de eventos ou curadoria manual

## Dados
Preços da vitrine vistos em 23/11/2026. Os textos de "Do arquivo" são datas reais de lançamento. A lista de bares é da matéria da CNN Brasil do Dia do Vinil.
