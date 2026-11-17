# Análise do Strava — 235 atividades

Arquivo: `dados/strava-atividades.json` (+ `dados/strava-atividades.csv`)
Obtido em: 17/11/2026 — endpoint interno `/athlete/training_activities` (console, conta gratuita)
Período coberto: **10/05/2024 → 14/09/2026** (o Strava deste atleta começa em 10/05/2024)

---

## 1. Resumo geral

| Métrica | Valor |
|---------|-------|
| Atividades totais | **235** |
| Corridas (Run) | **133** — 734,7 km |
| Caminhadas (Walk) | 31 |
| Treino funcional/workout | 44 |
| Musculação (WeightTraining) | 25 |
| Bike (Ride) | 1 |
| Trilha (Hike) | 1 |
| Distância total (todas) | **870,1 km** |
| Atividades por ano | 2024: 66 · 2025: 118 · 2026: 51 |

---

## 2. Novas provas achadas SÓ no Strava (não estavam nos 15 oficiais)

| Data | Atividade (nome no Strava) | Dist | Tempo | Ritmo aprox. | Link |
|------|----------------------------|------|-------|--------------|------|
| 04/04/2025 | **Nightrun ADRS – São Pedro** | 5,68 km | 37:32 | 6:35/km | `strava.com/activities/` (ver CSV) |
| 29/11/2025 | **Ultra Trail Ipeuna 5k** | 5,40 km | 29:04 | 5:23/km | id no CSV |
| 28/02/2026 | **TRIREX – 1ª Etapa** | 5,35 km | 28:18 | 5:16/km | id no CSV |
| 15/03/2026 | **ITA Trail Run – Etapa Fazenda Santa Júlia** | 4,86 km | 32:32 | 6:41/km | id no CSV |
| 31/05/2026 | **Open Séries – Etapa Relógio do Sol (Águas de São Pedro)** | 4,86 km | 26:52 | 5:31/km | id no CSV |

> Todas precisam de confirmação em fonte de cronometragem/oficial para virar "prova com evidência"
> (status hoje: `strava` — evidência do próprio registro do atleta).

---

## 3. Cruzamento: provas oficiais × Strava

**Registradas no Strava (mesma data):**

| Data | Prova oficial | Strava (nome) | Strava (dist/tempo) |
|------|---------------|---------------|---------------------|
| 18/10/2025 | São Vicente Uaiã Night Run | Corrida Uaçai Night Run - Americana | 5 km / 25:31 |
| 09/11/2025 | Corrida São Vicente do Alvinegro | CORRIDA DO ALVINEGRO XV DE PIRACICABA | 5,22 km / 27:34 |
| 30/11/2025 | Vamos Correr Capivari | Primeira Vamos Correr Capivari | 5,40 km / 28:21 |
| 14/12/2025 | Desafio São Pedro Run | Desafio São Pedro Run | 4,75 km / 23:56 |
| 31/12/2025 | 69ª Corrida da Virada | Corrida da Virada - Brotas | 4,65 km / 24:55 |
| 04/04/2026 | Run For Night Run | RunFor NightRun | 6,22 km / 32:43 |
| 19/04/2026 | GBC Trail Run 7ª ed. | GBC Trail Run Botucatu | 6,72 km / 40:49 |
| 13/09/2026 | Corrida DROGAL | 1 Corrida e Caminhada Geracao em Movimento Drogal | 10 km / 53:06 (bate 00:53:06 oficial) |

**Provas oficiais SEM registro no Strava** (não logadas pelo atleta):
10/11/2024 · 28/06/2026 · 02/08/2026 · 16/08/2026 · 23/08/2026 · 19/09/2026 ·
03/10/2026 (Outubro Rosa) · 11/10/2026 (GBC 8ª) · 08/11/2026 (Pata da Onça) · 15/11/2026 (Alvinegro)

> Observação: o Strava do Bruno **não tem atividades depois de 14/09/2026** — por isso as provas
> de out/nov/2026 não aparecem lá (só nas plataformas de cronometragem).

---

## 4. Os "treinos" citados no txt original — confirmação

| Treino citado no txt | Status | Evidência no Strava |
|----------------------|--------|---------------------|
| 15,86 km na Capim Fino | ✅ confirmado como **treino** | 04/06/2026 — "Treino Capim Fino" — 15,8 km / 1:45:22 |
| 17 km na Trilha dos Cavaleiros (+1.000 m) | ❌ não encontrado | ausente no período 05/2024→09/2026 |
| 20,5 km Represa do Patrimônio → Serra da Glória | ❌ não encontrado | ausente no período 05/2024→09/2026 |
| 20 km no TRIREX | ✅ oficial | 19/09/2026 — TRIREX 2ª etapa, 20 km, 02:05:27 |

**Maiores distâncias do histórico Strava:**
1. 17,67 km — 20/06/2026 — "Treino sábado em Ipeuna" (2:28:31)
2. 17,02 km — 06/06/2026 — "Treino de Sábado" (1:59:44)
3. 15,80 km — 04/06/2026 — "Treino Capim Fino" (1:45:22)
4. 12,02 km — 19/07/2026 — "Nike Run Club: domingo" (1:35:58)
5. 11,91 km — 31/03/2025 — "Corrida na Esteira" (1:00:00)

> Trilha dos Cavaleiros e Represa do Patrimônio provavelmente são de **antes de 10/05/2024**
> (início do Strava) ou de outro app. Pendente: perguntar ao atleta / verificar exportação antiga.

---

## 5. Observações para o HTML final

- Cada atividade tem `activity_url` (link da evidência) e `visibility` (todas `everyone`).
- Colunas do CSV: `data, hora, tipo, nome, dist_km, tempo, tempo_s, pace, elev_m, privado, visibility, url`.
- Ritmo calculado em `pace` (mm:ss/km).
- Atividades sem GPS (musculação/workout) ficam com `dist_km = 0` — manter no histórico como
  `tipo = treino_condicionamento`.
