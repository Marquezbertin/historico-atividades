# Log de Buscas — O que já foi varrido e o que falta

Projeto: histórico completo de atividades de Bruno Bertin Marquez (2021–2026)
Atualizado em: 17/11/2026

---

## ✅ Feito

### Strava
- [x] Perfil localizado: `https://www.strava.com/athletes/137173728`
- [x] `profileVisibilitySetting = "Everyone"` (perfil público), **mas** a lista de atividades
      exige login → raspagem externa impossível
- [x] API v3 sem token → 403; **API oficial exige assinatura paga desde jun/2026** → descartada
- [x] **Opção 3 executada (grátis):** script no console (`Sources → Snippets`, Ctrl+Enter) no
      endpoint interno `GET /athlete/training_activities?page=N&per_page=100` +
      header `X-Requested-With: XMLHttpRequest` → `dados/strava-atividades.json`
- [x] **235 atividades** baixadas e analisadas → `03-STRAVA-ANALISE.md`

### Open Results / Road Runners (RunnerHub)
- [x] Perfil agregado do atleta extraído por completo → **15 participações** (ver `01-HISTORICO.md`)
- [x] Endpoints descobertos:
  - `https://openresults.run/ajax_resultados_evento.cfm?id_evento=<id>&...&termo=<nome>&offset=0`
    (header `X-Requested-With: XMLHttpRequest`) → JSON com `html`, `recordsFiltered`
  - `https://openresults.run/resultados/bruno-bertin-marquez/` (página agregada)
  - `https://roadrunners.run/api/atletas_busca.cfm?busca=<termo>` exige headers
    `X-RR-Audience-Context` + `X-RR-Audience-Signature`
  - **Tokens de audiência capturados** (página `/busca/`, 17/11/2026):
    - `contextToken` = `eyJzY2hlbWFWZXJzaW9uIjoxLCJwYWdlVmlld0lkIjoiZGUzNDVhOTct...`
    - `signature` = `5f217d6aa2094ae2bbb8d3ee0964562a72fc409a318d3c529557f3f8f002d196`
    - (reextrair a cada sessão se expirar)
  - `/api/search.cfm` → 403 mesmo com headers

### RaveliSports — varredura completa
- [x] JSON de eventos: `https://ravelisports.com.br/session/20261117_ravelisports_events.json`
- [x] **181 arquivos `.clax`** (edições 2023 → 2026) baixados e varridos por "bertin"
- [x] Achados: **Desafio São Pedro Run 14/12/2025** (novo!) + Vamos Correr Capivari (já era #12)
- [x] Erenice BERTIN MARQUEZ (familiar) aparece — descartada do histórico

### Outras plataformas
- [x] **Cronoserv** — achada a **Corrida Outubro Rosa 03/10/2026** (novo!)
  - busca de atletas no site é via Livewire → sem endpoint público simples
- [x] **Global Cronometragem** — `/busca?q=` não indexa nomes de atletas; confirmou detalhes
      da 69ª Corrida da Virada (`resultado.php?id=447`)
- [x] **Apuração de Tempos** — Corrida Pata da Onça 2026 (novo!): resultados em
      `https://www.apuracaodetempos.com.br/Resultados/corridapatadaonca2026/Resultados.html`
- [x] Buscas web por nome completo / "Bertin Marquez" / "Bruno Bertin" + cidades
      (Piracicaba, São Pedro, Brotas, Americana, Capivari, Indaiatuba, Botucatu)
- [x] **A Tribuna Piracicaba** — 2 matérias úteis (pódio do Bruno no GBC 6K, 14/10/2026)

---

## ⏳ Pendente

### Varreduras restantes da internet (2021–2026)
- [ ] **Road Runners API** com os headers de audiência capturados →
      `resultados_busca.cfm`, `atletas_busca.cfm`, `eventos_busca.cfm` com termo "bertin"
      (varre todos os eventos, pode achar provas que o perfil agregado não linkou)
- [ ] **Cronoserv** — varrer eventos 2021–2026 em busca do nome
      (endpoint de busca de atletas a descobrir; hoje só temos o evento 3723)
- [ ] **RaveliSports 2021–2022** — o JSON atual cobre 2023+; procurar sessions antigas
- [ ] Outras cronometragens: Alcateia Crono (`alcateiacrono.com.br/resultados`),
      Corrida e Aventura (`inscricoes.corridaeaventura.com.br/resultados`),
      MySplit / Chip3 / ProRacing / Ficha de Corrida / Racetag / Chronoass
- [ ] Chelso Sports (organiza Alvinegro, Corrida Turística, Pague Menos, GBC) —
      verificar se publica resultados próprios fora do RunnerHub
- [ ] Notícias: `esportesaopedro.com.br` (portal do próprio Bruno — seções conquistas/atletas),
      site da Prefeitura de São Pedro, Jornal da Corrida, Contra Relógio
- [ ] Redes sociais: posts do Instagram `@bruno_bertin84` e do EMA (provas de 2021–2023)
- [ ] Facebook: grupos de corrida de Piracicaba/São Pedro (busca por nome)

### Dados do Strava a complementar
- [ ] Trilha dos Cavaleiros (17 km) e Represa do Patrimônio (20,5 km) — **não estão** no Strava
      10/05/2024→14/09/2026; perguntar ao atleta se são de antes de 10/05/2024 ou de outro app
- [ ] Localizar resultados oficiais das 5 novas provas achadas no Strava
      (Nightrun ADRS, Ultra Trail Ipeuna, TRIREX 1ª etapa, ITA F. Santa Júlia, Open Séries)

---

## 🧰 Atalhos / endpoints úteis descobertos

| Uso | Endpoint |
|-----|----------|
| Resultado por evento (Open Results) | `openresults.run/ajax_resultados_evento.cfm?id_evento=<id>&termo=<nome>&offset=0` |
| Busca atletas (Road Runners) | `roadrunners.run/api/atletas_busca.cfm?busca=<nome>` + headers `X-RR-Audience-Context/Signature` |
| Resultado ao vivo (Raveli) | `ravelisports.com.br/resultados/eventos/<ano>/<PROVA>/CORRIDA.clax` (XML) |
| Eventos Raveli | `ravelisports.com.br/session/<AAAA-MM-DD>_ravelisports_events.json` |
| Cronoserv evento | `cronoserv.com.br/evento/<id>?tab=result` · atleta `cronoserv.com.br/atleta/<evento>/<resultado>` |
| Global Cronometragem | `globalcronometragem.com.br/resultado.php?id=<n>` |
| Apuração de Tempos | `apuracaodetempos.com.br/Resultados/<slug>/Resultados.html` |
| Atividades Strava (conta gratuita) | `strava.com/athlete/training_activities?page=N&per_page=100` + `X-Requested-With: XMLHttpRequest` (via console/snippets) |

---

## 📁 Estrutura da pasta

```
projeto-historico-atividades/
├── 00-ESCOPO.md              ← escopo, objetivos, regras
├── 01-HISTORICO.md           ← atividades encontradas + evidências
├── 02-LOG-DE-BUSCAS.md       ← este arquivo
├── 03-STRAVA-ANALISE.md      ← análise das 235 atividades do Strava
├── dados/                    ← strava-atividades.json/.csv e cruudos
└── evidencias/               ← prints, HTMLs e arquivos de comprovação por atividade
```

---

## ✅ Concluído 17/11/2026 — Strava (235 atividades)

- [x] JSON recebido do usuário e movido para `dados/strava-atividades.json` (421 KB) + CSV gerado
- [x] 235 atividades: 133 corridas (734,7 km), 31 caminhadas, 44 workouts, 25 musculação, 1 bike, 1 hike
- [x] Período: 10/05/2024 → 14/09/2026 (Strava começa em 10/05/2024)
- [x] 8 provas oficiais conferem por data com atividade no Strava (Drogal bate exato 00:53:06)
- [x] 5 novas provas achadas SÓ no Strava (Nightrun ADRS 04/04/25, Ultra Trail Ipeuna 29/11/25,
      TRIREX 1ª etapa 28/02/26, ITA F. Santa Júlia 15/03/26, Open Séries Relógio do Sol 31/05/26)
- [x] Capim Fino confirmado como treino (04/06/2026, 15,8 km)
- [x] 10 provas oficiais sem registro no Strava (última atividade logada: 14/09/2026)
---

## ✅ Concluído 17/11/2026 — Chelso Sports (API pública) + RunnerHub

- [x] Descoberta a API pública da Chelso Sports (organiza TRIREX, GBC, Turística, Pague Menos,
      Alvinegro, Uaçai Night Run, Drogal, Meia Maratona de Piracicaba):
      `chelso.com.br/resultados/data/events.json` + `data/<id>/results.json` (70 eventos,
      jan/2025 → nov/2026). Sem chave, só `./data/`.
- [x] 10 registros de "BRUNO BERTIN MARQUEZ" extraídos → `dados/chelso-resultados.json`
- [x] **NOVO #19: TRIREX 1ª Etapa 28/02/2026** — 5KM, BIB 5391, líq 00:27:35, bruto 00:27:40,
      67º geral, 14º cat M-40-49, EMA (antes só constava no Strava com 28:18)
- [x] 8 provas existentes ganharam segunda fonte (Chelso confirma tempos exatos)
- [x] Descartado: "BRUNO BERTINI" no triathlon de Itatiba 05/10/2025 (outra pessoa)
- [x] RunnerHub esgotado: só 2 perfis (bruno-bertin-marquez = 15, bruno-bertin = 1);
      varredura com termo "bertin" nos eventos TRIREX/ITA/GBC/Ipeúna → nada novo
- [x] Raveli esgotado: JSON atual cobre só 2023–2026 (181 eventos já varridos)
- [x] Open Results: TRIREX 2026 1ª etapa consta como "resultados ainda não publicados"

---

## ✅ Concluído 17/11/2026 — Sincronia Crono & Consolidação Final

- [x] **CONFIRMADO OFICIAL #14: ITA Trail Run – Etapa Fazenda Santa Júlia (15/03/2026)**
  - Localizada a cronometragem oficial na **Sincronia Crono** (`https://sincroniacrono.com.br/ita-trail-run/`)
  - Dados oficiais: 6KM, BIB 616, tempo oficial **00:46:15**, ritmo 07:41 min/km, 29º Geral, equipe EMA.
- [x] Links diretos de atividades do Strava associados para todas as provas (inclusive Nightrun ADRS, Ultra Trail Ipeúna e Open Séries Relógio do Sol).
- [x] **HTML Final Moderno e Esportivo Gerado:**
  - `index.html` (para GitHub Pages) e `historico-bruno-bertin-marquez.html` com Dark Athletic UI, Hall da Fama de Recordes Pessoais, Cards das 23 Provas com comprovantes clicáveis, Feed completo das 235 atividades Strava, filtros e gráfico de evolução anual.
- [x] Pasta `evidencias/` alimentada com `comprovacao-provas-oficiais.json` e `resumo-evidencias.txt`.
- [x] `README.md` criado com documentação e tutorial para publicação imediata no GitHub Pages.
