# Projeto — Histórico Completo de Atividades de Bruno Bertin Marquez

**Atleta:** Bruno Bertin Marquez (Bruno Bertin) — 42 anos, M-40-44, São Pedro/SP
**Equipe:** EMA — Equipe Municipal de Atletismo de São Pedro
**Período do levantamento:** 2021 → 2026 (e treinos anteriores se existirem)
**Data de início do projeto:** 17/11/2026

---

## 1. Objetivo

Montar um **histórico completo e comprovado** de todas as atividades físicas do Bruno
(provas oficiais, trilhas e treinos), cada uma com **evidência/link da fonte**, e ao final
gerar um **arquivo HTML** navegável que sirva de comprovação activity por activity.

## 2. Escopo

### Entra no escopo
- Provas oficiais de rua e trail (5K, 6K, 10K, 15K, 20K, 21K, 42K) — 2021 a 2026.
- Resultados de plataformas de cronometragem (chip, tempos oficiais, categorias, BIBs).
- Treinos e atividades registrados no Strava (corridas, trilhas, longões).
- Evidência por atividade: URL da fonte, data, distância, tempo, ritmo, categoria/colocação.

### Fora do escopo
- Atividades de terceiros (mesmo que apareçam nos mesmos eventos).
- Dados pessoais não relacionados à atividade física.

## 3. Entregáveis

| # | Entregável | Status |
|---|------------|--------|
| 1 | Pasta do projeto com tudo registrado | ✅ Concluído |
| 2 | Lista das provas oficiais com evidência | ✅ Concluído (23 provas registradas e auditadas) |
| 3 | Treinos Strava (200+) importados em lote | ✅ Concluído (235 atividades, JSON/CSV em `dados/`) |
| 4 | Varredura restante da internet (2021–2026) | ✅ Concluído (Open Results, Chelso, Sincronia, Raveli, Cronoserv, Global, Apuração) |
| 5 | **HTML final com evidência de cada atividade** | ✅ Concluído (`index.html` e `historico-bruno-bertin-marquez.html` prontos para GitHub Pages) |

## 4. Fontes de dados

### 4.1 Strava (treinos + provas) — via API (Opção 2 escolhida)
- Perfil: `https://www.strava.com/athletes/137173728` (perfil público, mas atividades exigem login).
- Método: app de API gratuito criado pelo usuário em `strava.com/settings/api`
  (Authorization Callback URL: `http://localhost`).
- **Pendente:** usuário vai informar `client_id` e `client_secret`.
- Em seguida: gero a URL de autorização → usuário aprova → devolve o `code` da URL →
  troco por token → baixo todas as páginas de `/api/v3/athlete/activities` (200/página)
  → salvo JSON/CSV em `dados/`.
- Escopo de permissão: `activity:read_all,profile:read_all`.

### 4.2 Resultados oficiais
- **Open Results / Road Runners (RunnerHub)** — perfil agregado do atleta (15 participações).
- **RaveliSports** — 181 arquivos `.clax` varridos (edições 2023–2026).
- **Cronoserv** — cronometragem de Indaiatuba/SP.
- **Global Cronometragem** — Corrida da Virada (Brotas).
- **Apuração de Tempos** — Corrida Pata da Onça (Brotas).
- Buscas web genéricas por nome + varredura de notícias regionais.

### 4.3 Notícias / redes
- A Tribuna Piracicaba (busca "Bertin").
- Portal `esportesaopedro.com.br` (criado pelo próprio Bruno).
- Instagram `@bruno_bertin84`.

## 5. Critérios de evidência (para o HTML final)

Cada atividade no HTML final deve conter, no mínimo:
1. Data
2. Nome da prova / atividade
3. Cidade/UF
4. Distância
5. Tempo (líquido e bruto quando houver)
6. Ritmo
7. Categoria e colocação (quando houver)
8. **Link da fonte** (evidência clicável) + data da consulta
9. Tipo: `oficial` (cronometragem) ou `treino` (Strava)

## 6. Regras de privacidade
- Nada de senhas, tokens ou credenciais ficam neste repositório.
- O `client_secret` só é usado em memória/variável local, nunca gravado em arquivo versionado.
- O HTML final mostra apenas dados esportivos públicos do próprio atleta.
