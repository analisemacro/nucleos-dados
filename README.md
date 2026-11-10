# nucleos-dados

Atualização automática dos **núcleos de inflação do IPCA** usados pelo
[MCP Análise Macro](https://nucleos-mcp.analisemacro.workers.dev/mcp).

- **Cálculo:** pacote R [`nucleos`](https://github.com/vitorwilher/nucleos), que
  reproduz as séries analíticas da Nota Técnica 57 do Banco Central (conferidas
  contra o SGS).
- **Orquestração:** `.github/workflows/atualizar-dados.yaml` roda nos dias 7 a 16
  de cada mês, verifica se o IBGE divulgou um IPCA novo e, só então, calcula e
  publica `series_nucleos.{json,csv,rds}` no release
  [`dashboard-dados`](../../releases/tag/dashboard-dados).
- **Forçar uma atualização:** Actions → *atualizar-dados* → *Run workflow* →
  marcar *forcar*.
