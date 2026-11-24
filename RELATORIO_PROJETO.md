# RelatÃ³rio Completo do Projeto BettaFish BR

## VisÃ£o Geral

PortaÃ§Ã£o completa do sistema BettaFish (originalmente chinÃªs) para o mercado brasileiro e latino-americano, incluindo traduÃ§Ã£o, adaptaÃ§Ã£o de APIs, fontes de dados e interface.

---

## 1. O que Ã© o BettaFish

Sistema multi-agente de anÃ¡lise de opiniÃ£o pÃºblica que utiliza IA para coletar, analisar e gerar relatÃ³rios sobre qualquer tema. Originalmente desenvolvido para o mercado chinÃªs pelo repositÃ³rio [666ghj/BettaFish](https://github.com/666ghj/BettaFish).

### Arquitetura dos Engines

```
UsuÃ¡rio digita pergunta
        â”‚
        â”œâ”€â”€â†’ InsightEngine (banco local)  â”€â”€â”
        â”œâ”€â”€â†’ MediaEngine (web multimodal)  â”€â”€â”¼â”€â”€â†’ ForumEngine (debate) â”€â”€â†’ ReportEngine (relatÃ³rio)
        â””â”€â”€â†’ QueryEngine (web textual)    â”€â”€â”˜
```

| Engine | Porta | FunÃ§Ã£o |
|--------|-------|--------|
| **InsightEngine** | 8501 | Minera o banco de dados local (PostgreSQL). AnÃ¡lise de sentimento. |
| **MediaEngine** | 8502 | Busca multimodal na web (Tavily). Analisa imagens e vÃ­deos. |
| **QueryEngine** | 8503 | Busca textual na web (Tavily). Pesquisa artigos e notÃ­cias. |
| **ForumEngine** | - | Moderador de debates entre os agentes. |
| **ReportEngine** | - | Gera relatÃ³rio final em HTML/PDF com grÃ¡ficos e tabelas. |
| **MindSpider** | - | Crawler que coleta dados de notÃ­cias e redes sociais. |

---

## 2. O que foi feito

### Fase 0 â€” TraduÃ§Ã£o completa (161+ arquivos)
- README.md e todos os sub-READMEs traduzidos para PT-BR
- Interface web (templates/index.html) traduzida
- Todos os arquivos Python: comentÃ¡rios, logs, prompts, docstrings
- Arquivos de configuraÃ§Ã£o (.env.example)

### Fase 1 â€” Busca web global
- MediaEngine agora usa **Tavily** como provedor padrÃ£o (substituindo Bocha chinesa)
- Classe `TavilyMultimodalSearch` criada com mesma interface da `BochaMultimodalSearch`
- Prompts atualizados com plataformas ocidentais (Twitter, Instagram, YouTube, TikTok, Reddit)
- GÃ­rias e exemplos brasileiros nos prompts

### Fase 2 â€” Fontes de notÃ­cias internacionais
- **24 fontes RSS** substituindo as 12 chinesas, organizadas por regiÃ£o:
  - **Brasil** (6): G1, Folha, EstadÃ£o, UOL, Valor EconÃ´mico, InfoMoney
  - **EUA** (4): Reuters, AP, CNN, NYT
  - **Europa** (4): BBC, DW, France24, Euronews
  - **AmÃ©rica do Sul** (9): ClarÃ­n, EMOL, El Tiempo, El Comercio, El PaÃ­s, ABC Color, El Deber, El Universo, Ãšltimas NotÃ­cias
  - **Global** (1): GitHub Trending
- Painel de configuraÃ§Ã£o na interface com toggles por regiÃ£o
- Endpoints `/api/update-news` e `/api/news-status`
- Coleta via RSS feeds (sem dependÃªncia de API chinesa)

### Fase 3 â€” AnÃ¡lise de sentimento em portuguÃªs
- Modelo `tabularisai/multilingual-sentiment-analysis` jÃ¡ suporta portuguÃªs nativamente
- Testes e prompts atualizados para portuguÃªs
- Labels de sentimento em PT-BR: muito negativo, negativo, neutro, positivo, muito positivo

### Infraestrutura Docker
- Imagem Docker local (`bettafish:local`) com cÃ³digo traduzido
- CorreÃ§Ã£o de `host.docker.internal` no Linux via `extra_hosts`
- `.dockerignore` atualizado para excluir db_data e logs do build
- Volumes montados para logs, relatÃ³rios e configuraÃ§Ã£o

---

## 3. ConfiguraÃ§Ã£o e Uso

### PrÃ©-requisitos
- Docker e Docker Compose
- Ollama rodando localmente (ou outra API compatÃ­vel com OpenAI)

### InstalaÃ§Ã£o rÃ¡pida

```bash
# Clonar o repositÃ³rio
git clone git@github.com:linnoff88-dev/BettaFish.git
cd BettaFish

# Criar arquivo de configuraÃ§Ã£o
cp .env.example .env
# Editar .env com suas configuraÃ§Ãµes (ver seÃ§Ã£o abaixo)

# Build e iniciar
docker compose build
docker compose up -d
```

### ConfiguraÃ§Ã£o do .env

```bash
# ====================== BANCO DE DADOS ======================
DB_HOST=db
DB_PORT=5432
DB_USER=bettafish
DB_PASSWORD=bettafish
DB_NAME=bettafish
DB_DIALECT=postgresql

# ====================== POSTGRES CONTAINER ======================
POSTGRES_USER=bettafish
POSTGRES_PASSWORD=bettafish
POSTGRES_DB=bettafish

# ======================= LLMs =======================
# Timeout aumentado para modelos locais
LLM_REQUEST_TIMEOUT=3600

# Com Ollama local (recomendado qwen2.5:32b para 3 engines em paralelo)
INSIGHT_ENGINE_API_KEY=ollama
INSIGHT_ENGINE_BASE_URL=http://host.docker.internal:11434/v1
INSIGHT_ENGINE_MODEL_NAME=qwen2.5:32b

MEDIA_ENGINE_API_KEY=ollama
MEDIA_ENGINE_BASE_URL=http://host.docker.internal:11434/v1
MEDIA_ENGINE_MODEL_NAME=qwen2.5:32b

QUERY_ENGINE_API_KEY=ollama
QUERY_ENGINE_BASE_URL=http://host.docker.internal:11434/v1
QUERY_ENGINE_MODEL_NAME=qwen2.5:32b

REPORT_ENGINE_API_KEY=ollama
REPORT_ENGINE_BASE_URL=http://host.docker.internal:11434/v1
REPORT_ENGINE_MODEL_NAME=qwen2.5:32b

FORUM_HOST_API_KEY=ollama
FORUM_HOST_BASE_URL=http://host.docker.internal:11434/v1
FORUM_HOST_MODEL_NAME=qwen2.5:32b

KEYWORD_OPTIMIZER_API_KEY=ollama
KEYWORD_OPTIMIZER_BASE_URL=http://host.docker.internal:11434/v1
KEYWORD_OPTIMIZER_MODEL_NAME=qwen2.5:32b

# ================== BUSCADORES ====================
TAVILY_API_KEY=sua_chave_tavily_aqui
SEARCH_TOOL_TYPE=TavilyAPI
```

#### Nota sobre modelos
- **qwen2.5:32b** â€” Recomendado para rodar 3 engines em paralelo com Ollama local
- **qwen2.5:72b** â€” Melhor qualidade mas causa timeout com 3 engines simultÃ¢neos
- Pode usar qualquer API compatÃ­vel com formato OpenAI (GPT-4o, Claude, DeepSeek, etc.)

### Uso

1. Acesse **http://localhost:5000**
2. Clique no Ã­cone de **engrenagem** (configuraÃ§Ãµes)
3. Clique em **"Salvar e iniciar sistema"** (nÃ£o apenas "Salvar")
4. Aguarde os 3 engines iniciarem (~30 segundos)
5. Digite sua consulta na caixa de texto e envie
6. Aguarde o processamento (5-30 min dependendo do modelo)
7. O relatÃ³rio serÃ¡ gerado automaticamente em HTML/PDF

### Painel de Fontes de NotÃ­cias
- Na engrenagem, role atÃ© "Fontes de NotÃ­cias"
- Ative/desative regiÃµes (Brasil, EUA, Europa, AmÃ©rica do Sul)
- Clique "Atualizar NotÃ­cias" para coletar RSS

### Portas

| Porta | ServiÃ§o |
|-------|---------|
| 5000 | Interface web (Flask) |
| 8501 | InsightEngine (Streamlit) |
| 8502 | MediaEngine (Streamlit) |
| 8503 | QueryEngine (Streamlit) |
| 5444 | PostgreSQL |

---

## 4. O que funciona agora

| Recurso | Status |
|---------|--------|
| Busca web global (Tavily) | Funciona |
| Busca multimodal (Tavily) | Funciona |
| Debate entre agentes (ForumEngine) | Funciona |
| GeraÃ§Ã£o de relatÃ³rios HTML/PDF | Funciona |
| Coleta de notÃ­cias RSS (24 fontes) | Funciona |
| AnÃ¡lise de sentimento em portuguÃªs | Funciona |
| Interface web em portuguÃªs | Funciona |
| LLM via Ollama local | Funciona |

---

## 5. O que ainda nÃ£o funciona (Fase 4 â€” Pendente)

| Recurso | Motivo |
|---------|--------|
| Coleta de posts do Twitter/X, Instagram, Reddit, YouTube | Crawlers nÃ£o implementados |
| Coleta de comentÃ¡rios de redes sociais | Sem crawler para plataformas ocidentais |
| AnÃ¡lise de volume estatÃ­stico massivo | InsightEngine depende de dados coletados |
| ComparaÃ§Ã£o entre plataformas | Sem dados de mÃºltiplas redes |

### Plano da Fase 4 â€” Crawlers Ocidentais

Abordagem hÃ­brida: **Apify + APIs oficiais** (~6 dias, ~$540/mÃªs)

| Plataforma | Ferramenta | Custo/mÃªs |
|-----------|-----------|----------|
| Reddit | PRAW (API oficial) | $0 |
| YouTube | Google API v3 | $0 |
| Twitter/X | Apify (Tweet Scraper) | ~$60 |
| Instagram | Apify (Instagram Scraper) | ~$225 |
| TikTok | Apify (TikTok Scraper) | ~$255 |

Firecrawl foi descartado (bloqueia redes sociais). LinkedIn nÃ£o recomendado (risco legal).

---

## 6. Problemas conhecidos e soluÃ§Ãµes

| Problema | SoluÃ§Ã£o |
|----------|---------|
| `host.docker.internal` nÃ£o resolve no Linux | Adicionado `extra_hosts: host.docker.internal:host-gateway` no docker-compose.yml |
| MediaEngine exigia Bocha API | Adicionado suporte a TavilyAPI no Streamlit app e config |
| Timeout com qwen2.5:72b (3 engines paralelos) | Usar qwen2.5:32b + LLM_REQUEST_TIMEOUT=3600 |
| Interface mostra mensagens antigas apÃ³s restart | Recarregar pÃ¡gina (F5) |
| Logs em chinÃªs no container | Rebuildar imagem com `docker compose build` |
| Sistema nÃ£o aceita consultas | Clicar "Salvar e iniciar sistema" (nÃ£o apenas "Salvar") |

---

## 7. Estrutura de arquivos modificados

```
BettaFish/
â”œâ”€â”€ README.md                    # Traduzido + seÃ§Ã£o de infraestrutura
â”œâ”€â”€ RELATORIO_PROJETO.md         # Este documento
â”œâ”€â”€ .env.example                 # Traduzido
â”œâ”€â”€ .dockerignore                # Atualizado (exclui db_data, logs)
â”œâ”€â”€ docker-compose.yml           # Build local + extra_hosts + volumes
â”œâ”€â”€ config.py                    # TavilyAPI como opÃ§Ã£o
â”œâ”€â”€ app.py                       # Traduzido + endpoints /api/update-news e /api/news-status
â”œâ”€â”€ templates/index.html         # Interface PT-BR + painel de notÃ­cias
â”œâ”€â”€ SingleEngineApp/
â”‚   â”œâ”€â”€ media_engine_streamlit_app.py   # Suporte TavilyAPI
â”‚   â”œâ”€â”€ query_engine_streamlit_app.py   # Traduzido
â”‚   â””â”€â”€ insight_engine_streamlit_app.py # Traduzido
â”œâ”€â”€ InsightEngine/               # Prompts com plataformas ocidentais
â”œâ”€â”€ MediaEngine/                 # TavilyMultimodalSearch adicionado
â”œâ”€â”€ QueryEngine/                 # Traduzido
â”œâ”€â”€ ReportEngine/                # Traduzido
â”œâ”€â”€ ForumEngine/                 # Traduzido
â”œâ”€â”€ MindSpider/
â”‚   â””â”€â”€ BroadTopicExtraction/
â”‚       â””â”€â”€ get_today_news.py    # 24 fontes RSS (BR/USA/EU/LATAM)
â””â”€â”€ SentimentAnalysisModel/      # Modelo multilÃ­ngue suporta PT
```

---

## 8. Custo de tokens e comparativo de LLMs

Cada relatÃ³rio completo consome aproximadamente **620.000 tokens** (~430K input + ~190K output) distribuÃ­dos em ~110-120 chamadas LLM entre os engines.

### DistribuiÃ§Ã£o de tokens por componente

| Componente | Chamadas LLM | Tokens estimados |
|-----------|-------------|-----------------|
| InsightEngine | ~32 | ~144.000 |
| QueryEngine | ~32 | ~144.000 |
| MediaEngine | ~32 | ~144.000 |
| ReportEngine | ~15-20 | ~160.000 |
| ForumEngine | ~5-10 | ~30.000 |
| **Total** | **~110-120** | **~620.000** |

### Custo por relatÃ³rio em APIs comerciais

| Modelo | Custo/relatÃ³rio | Tempo | Qualidade |
|--------|----------------|-------|-----------|
| Ollama local (qwen2.5:32b) | $0.00 | 3-4 horas | MÃ©dia |
| DeepSeek Chat | $0.11 | 8-12 min | Boa |
| GPT-4o-mini | $0.17 | 5-8 min | Boa |
| Claude Haiku 3.5 | $1.10 | 8-12 min | Boa |
| GPT-4o | $2.98 | 10-15 min | Muito boa |
| Claude Sonnet 4 | $4.14 | 10-15 min | Excelente |

### ProjeÃ§Ã£o de custo mensal (100 relatÃ³rios/mÃªs)

| Modelo | Custo mensal |
|--------|-------------|
| Ollama local | $0 (sÃ³ energia elÃ©trica) |
| DeepSeek Chat | ~$11 |
| GPT-4o-mini | ~$17 |
| Claude Haiku 3.5 | ~$110 |
| GPT-4o | ~$298 |
| Claude Sonnet 4 | ~$414 |

> **Nota:** Todos os modelos usam formato OpenAI-compatible. Basta trocar `API_KEY`, `BASE_URL` e `MODEL_NAME` no `.env` para alternar entre provedores. Pode usar modelos diferentes por engine (ex: DeepSeek para engines de busca, GPT-4o para o ReportEngine).

---

## 9. RepositÃ³rio

- **Origem**: [666ghj/BettaFish](https://github.com/666ghj/BettaFish) (chinÃªs)
- **Fork adaptado**: [linnoff88-dev/BettaFish](https://github.com/linnoff88-dev/BettaFish) (portuguÃªs brasileiro)
