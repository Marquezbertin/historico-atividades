# 🏃‍♂️ Bruno Bertin Marquez — Histórico Esportivo & Provas Oficiais

> Portal oficial e auditado com o histórico completo de corridas, competições e treinos do atleta **Bruno Bertin Marquez** (EMA — Equipe Municipal de Atletismo de São Pedro/SP).

---

## ⚡ Destaques do Atleta

- **Atleta:** Bruno Bertin Marquez (Bruno Bertin)
- **Categoria:** M 40-44 (Nasc. 25/03/1984)
- **Equipe:** EMA — Equipe Municipal de Atletismo de São Pedro / Prefeitura de São Pedro
- **Cidade:** São Pedro / SP
- **Total de Provas Auditadas:** **24 provas** (100% comprovadas com chips de cronometragem eletrônica, rankings oficiais e Strava)
- **Total de Atividades no Strava:** **235 atividades** (734,7 km de corrida / 870,1 km no total)

### 🏆 Recordes Pessoais Oficiais (PRs)
- **5 km (Asfalto):** **23:31** (Pace 4:42 /km) — *Desafio São Pedro Run (14/12/2025)* — 30º Geral (de 259), 6º Categoria
- **6 km (Asfalto):** **31:57** (Pace 5:20 /km) — *Corrida Pata da Onça Brotas (08/11/2026)* — 74º Geral, 9º Categoria
- **6 km (Trail Run):** **41:28** (Pace 6:55 /km) — *GBC Trail Run 7ª Edição Botucatu (19/04/2026)* — 58º Geral, 5º Categoria
- **10 km (Asfalto):** **50:15** (Pace 5:01 /km) — *Eco Run Piracicaba 2026 (16/08/2026)* — 169º Geral, 32º Categoria
- **11 km (Trail Run):** **01:16:30** (Pace 6:57 /km) — *UTI Ultra Trail Ipeúna (21/11/2026)* — 19º Geral Masc, 4º Categoria (Top 4)
- **20 km (Trail Run):** **02:05:27** (Pace 6:16 /km) — *TRIREX Endurance 2ª Etapa Brotas (19/09/2026)* — 92º Geral, 27º Categoria
- **Pódio de Destaque:** 🥉 **3º Lugar na Categoria 40-44** no *GBC Trail Run 8ª Edição Indiana (11/10/2026)*

---

## 🌐 Visualização do Site / Dashboard Esportivo

O projeto conta com um **dashboard esportivo interativo moderno**, responsivo para mobile e desktop, desenvolvido com tema esportivo escuro (Dark Athletic UI inspirado no Strava, Nike Run Club e Garmin Connect).

- Arquivo principal: `index.html` (pronto para GitHub Pages)
- Arquivo espelho: `historico-bruno-bertin-marquez.html`

### Funcionalidades do Site:
1. **Cards das 24 Provas Oficiais** com chips de ritmo, tempo líquido, colocação geral e na categoria, BIB e botões diretos para os resultados oficiais.
2. **Alternador de Visualização:** Modo Cards Visuais vs Modo Tabela Completa.
3. **Filtros Dinâmicos:** Busca em tempo real por nome/cidade, filtro por ano (2024, 2025, 2026), distância (5K, 6K, 10K, 11K, 20K) e terreno (Asfalto vs Trilha).
4. **Feed do Strava (235 Atividades):** Tabela completa com filtros por esporte e identificação visual de quais atividades foram provas oficiais.
5. **Gráfico de Volume Anual:** Comparativo de quilometragem percorrida mês a mês e ano a ano.

---

## 📁 Estrutura de Arquivos

```
projeto-historico-atividades/
├── index.html                           ← Portal web principal (pronto para GitHub Pages)
├── historico-bruno-bertin-marquez.html   ← Cópia espelho do portal
├── README.md                            ← Documentação principal do repositório
├── 00-ESCOPO.md                         ← Definição de escopo e entregáveis
├── 01-HISTORICO.md                      ← Detalhamento prova a prova com links de fontes
├── 02-LOG-DE-BUSCAS.md                  ← Registro de auditoria das plataformas varridas
├── 03-STRAVA-ANALISE.md                 ← Análise estatística das 235 atividades Strava
├── dados/                               ← Arquivos de dados brutos e estruturados
│   ├── strava-atividades.json           ← JSON com as 235 atividades do Strava
│   ├── strava-atividades.csv            ← CSV tabular das atividades
│   ├── chelso-resultados.json           ← Resultados oficiais extraídos da Chelso Sports
│   └── openresults-eventos.json         ← Endpoints de eventos do Open Results
└── evidencias/                          ← Arquivos de comprovação e registros offline
```

---

## 🚀 Como Publicar no GitHub Pages (Passo a Passo)

1. Crie um repositório no seu GitHub (exemplo: `historico-atividades` ou `atleta-bruno-bertin`).
2. No seu terminal, dentro desta pasta:
   ```bash
   git init
   git add .
   git commit -m "Histórico esportivo completo - Bruno Bertin Marquez"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git
   git push -u origin main
   ```
3. No GitHub:
   - Acesse **Settings** (Configurações do Repositório) → **Pages**.
   - Em **Build and deployment** > **Source**, selecione **Deploy from a branch**.
   - Escolha o branch `main` e pasta `/ (root)` e clique em **Save**.
4. Em cerca de 1 minuto, seu site estará no ar gratuitamente na URL:
   `https://SEU_USUARIO.github.io/NOME_DO_REPOSITORIO/`
