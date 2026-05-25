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

## Fontes de dados
- **Aba `Facebook`** (gid=609054384) — Meta Ads (todas as campanhas)
- **Aba `Google`** (gid=0) — Google Ads, **apenas SEARCH** (filtro `/SEARCH/i` aplicado em `Campaign Name`)
- **Aba `Budgets`** (opcional) — orçamentos por campanha. Estrutura mínima:
  ```
  Campaign | Budget
  Total    | 10000
  G77_LEAD_FRIO_AUTO_CWB | 3000
  ```
  Linha com Campaign=`Total` define o budget master. Outras linhas viram progress bars por campanha.

## Filtro de data
Chips no topo: **Hoje · Últimas 24h · 7 dias · 14 dias · 30 dias · 90 dias** + inputs **De/Até** pra range custom. Todo filtro reseta charts, KPIs, funil e tabelas.

## Preview de criativo
Auto-detecta coluna de imagem na planilha (qualquer header com `image`/`imagem`/`thumb`/`preview`/`capa`/`foto`/`asset` ou valor com extensão `.jpg/.png/.gif/.webp`). Quando presente, thumbnails 48x48 aparecem ao lado do nome do criativo + click abre lightbox em fullscreen.

Investimento (R$) é calculado como `(Impressões / 1000) × CPM` para ambas as plataformas, já que o sheet não tem coluna de Spend explícita.

### Google Search — keyword-level
A aba `Google` tá em granularidade de keyword (linhas = Date × Campaign × Ad Group × Keyword). A dashboard usa essa estrutura assim:
- **Top Palavras-chave**: tabela rankeável por impressões/cliques/CTR/conv./investimento, mostrando keyword + match type (EXACT/PHRASE/BROAD) + ad group + métricas
- **Tipo de Correspondência**: donut chart com share de impressões/cliques por match type
- A seção **Top Criativos** mostra apenas Meta Ads (ad name vazio no export padrão do Google Ads para RSAs)

### Visibilidade dinâmica por filtro de plataforma
- **Todas**: tudo visível (Top Criativos Meta + Top Keywords Google + FEED/STORIES + Match Type)
- **Meta**: esconde Keywords e Match Type
- **Google**: esconde Top Criativos e FEED/STORIES

## Filtro de plataforma
A dashboard tem 3 modos no topo: **Todas as plataformas / Meta Ads / Google Ads** — todos os gráficos e tabelas se atualizam dinamicamente.

## Link de criativo (auto-detectado)
Quando você adicionar uma coluna com URLs dos criativos na planilha, a dashboard detecta automaticamente:
- Qualquer header contendo `link`, `url`, `criativo` ou `creative` (case-insensitive)
- Ou qualquer coluna cujo valor seja um URL válido (`https://...`)

Nomes de criativos na seção "Top Criativos" viram **clicáveis** (abrem em nova aba) assim que houver link disponível.

## KPIs exibidos
- Investimento total (com breakdown Meta vs Google)
- Impressões, Cliques, CTR, CPM, CPC
- Leads (CP01 do Meta + Conversões do Google), CPL, Taxa de conversão
- Funil completo (Impressão → Click → [LPV] → Lead)
- Comparativo Meta vs Google (investimento, CTR, CPL, conversões)
- Performance temporal por dia (com linhas separadas por plataforma)
- Distribuição por campanha (FRIO / WARM / QUENTE)
- Posicionamento FEED vs STORIES (Meta)
- Ranking de criativos e adsets
- Insights automáticos (plataforma vencedora, melhor/pior criativo, alertas de tracking)

---
Feito por **GROWTH77** — Acquisition Agency.
