# Dashboard ClickPlanos — Growth77

Dashboard de aquisição paga (Meta Ads) construída pela **Growth77** para o cliente **ClickPlanos**.

## Live
Após habilitar GitHub Pages, a dashboard fica disponível em:
`https://brunoclemos.github.io/growth77-dashboard-clickplanos/`

## Como funciona
- **100% estática** — HTML + CSS + JS sem build step
- **Dados em tempo real** — puxa CSV publicado do Google Sheets a cada load (ou clique em "Atualizar")
- **Stack**: Tailwind CDN, Chart.js, PapaParse

## Atualizar dados
Os dados vêm direto da planilha do cliente. Qualquer alteração na planilha aparece na dashboard ao recarregar.

## KPIs exibidos
- Impressões, Investimento, Cliques, CTR
- Landing Page Views, Leads (CP01), CPL, Taxa de conversão geral
- Funil completo (Impressão → Click → LPV → Lead)
- Performance temporal por dia
- Distribuição por campanha (FRIO / WARM / QUENTE)
- Posicionamento FEED vs STORIES
- Ranking de criativos e adsets
- Insights automáticos (melhor/pior criativo, vencedor de placement, alertas de tracking)

---
Feito por **GROWTH77** — Acquisition Agency.
