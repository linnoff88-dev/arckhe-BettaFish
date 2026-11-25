ï»¿# RelatêÂ³rio Completo do Projeto BettaFish BR

## VisêÂ£o Geral

PortaêÂ§êÂ£o completa do sistema BettaFish (originalmente chinêÂªs) para o mercado brasileiro e latino-americano, incluindo traduêÂ§êÂ£o, adaptaêÂ§êÂ£o de APIs, fontes de dados e interface.

---

## 1. O que êÂ© o BettaFish

Sistema multi-agente de anêÂ¡lise de opiniêÂ£o pêÂºblica que utiliza IA para coletar, analisar e gerar relatêÂ³rios sobre qualquer tema. Originalmente desenvolvido para o mercado chinêÂªs pelo repositêÂ³rio [666ghj/BettaFish](https://github.com/666ghj/BettaFish).

### Arquitetura dos Engines

```
UsuêÂ¡rio digita pergunta
        ê¢ââ
        ê¢âÅê¢ââ¬ê¢ââ¬ê¢â â InsightEngine (banco local)  ê¢ââ¬ê¢ââ¬ê¢âÂ
        ê¢âÅê¢ââ¬ê¢ââ¬ê¢â â MediaEngine (web multimodal)  ê¢ââ¬ê¢ââ¬ê¢âÂ¼ê¢ââ¬ê¢ââ¬ê¢â â ForumEngine (debate) ê¢ââ¬ê¢ââ¬ê¢â â ReportEngine (relatêÂ³rio)
        ê¢ââê¢ââ¬ê¢ââ¬ê¢â â QueryEngine (web textual)    ê¢ââ¬ê¢ââ¬ê¢âË
```

| Engine | Porta | FunêÂ§êÂ£o |
|--------|-------|--------|
| **InsightEngine** | 8501 | Minera o banco de dados local (PostgreSQL). AnêÂ¡lise de sentimento. |
| **MediaEngine** | 8502 | Busca multimodal na web (Tavily). Analisa imagens e vêÂ­deos. |
| **QueryEngine** | 8503 | Busca textual na web (Tavily). Pesquisa artigos e notêÂ­cias. |
| **ForumEngine** | - | Moderador de debates entre os agentes. |
| **ReportEngine** | - | Gera relatêÂ³rio final em HTML/PDF com grêÂ¡ficos e tabelas. |
| **MindSpider** | - | Crawler que coleta dados de notêÂ­cias e redes sociais. |

---

## 2. O que foi feito

### Fase 0 ê¢â¬â TraduêÂ§êÂ£o completa (161+ arquivos)
- README.md e todos os sub-READMEs traduzidos para PT-BR
- Interface web (templates/index.html) traduzida
- Todos os arquivos Python: comentêÂ¡rios, logs, prompts, docstrings
- Arquivos de configuraêÂ§êÂ£o (.env.example)

### Fase 1 ê¢â¬â Busca web global
- MediaEngine agora usa **Tavily** como provedor padrêÂ£o (substituindo Bocha chinesa)
- Classe `TavilyMultimodalSearch` criada com mesma interface da `BochaMultimodalSearch`
- Prompts atualizados com plataformas ocidentais (Twitter, Instagram, YouTube, TikTok, Reddit)
- GêÂ­rias e exemplos brasileiros nos prompts

### Fase 2 ê¢â¬â Fontes de notêÂ­cias internacionais
- **24 fontes RSS** substituindo as 12 chinesas, organizadas por regiêÂ£o:
  - **Brasil** (6): G1, Folha, EstadêÂ£o, UOL, Valor EconêÂ´mico, InfoMoney
  - **EUA** (4): Reuters, AP, CNN, NYT
  - **Europa** (4): BBC, DW, France24, Euronews
  - **AmêÂ©rica do Sul** (9): ClarêÂ­n, EMOL, El Tiempo, El Comercio, El PaêÂ­s, ABC Color, El Deber, El Universo, êÅ¡ltimas NotêÂ­cias
  - **Global** (1): GitHub Trending
- Painel de configuraêÂ§êÂ£o na interface com toggles por regiêÂ£o
- Endpoints `/api/update-news` e `/api/news-status`
- Coleta via RSS feeds (sem dependêÂªncia de API chinesa)

### Fase 3 ê¢â¬â AnêÂ¡lise de sentimento em portuguêÂªs
- Modelo `tabularisai/multilingual-sentiment-analysis` jêÂ¡ suporta portuguêÂªs nativamente
- Testes e prompts atualizados para portuguêÂªs
- Labels de sentimento em PT-BR: muito negativo, negativo, neutro, positivo, muito positivo

### Infraestrutura Docker
- Imagem Docker local (`bettafish:local`) com cêÂ³digo traduzido
- CorreêÂ§êÂ£o de `host.docker.internal` no Linux via `extra_hosts`
- `.dockerignore` atualizado para excluir db_data e logs do build
- Volumes montados para logs, relatêÂ³rios e configuraêÂ§êÂ£o

---

## 3. ConfiguraêÂ§êÂ£o e Uso

### PrêÂ©-requisitos
- Docker e Docker Compose
- Ollama rodando localmente (ou outra API compatêÂ­vel com OpenAI)

### InstalaêÂ§êÂ£o rêÂ¡pida

```bash
# Clonar o repositêÂ³rio
git clone git@github.com:linnoff88-dev/BettaFish.git
cd BettaFish

# Criar arquivo de configuraêÂ§êÂ£o
cp .env.example .env
# Editar .env com suas configuraêÂ§êÂµes (ver seêÂ§êÂ£o abaixo)

# Build e iniciar
docker compose build
docker compose up -d
```

### ConfiguraêÂ§êÂ£o do .env

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
- **qwen2.5:32b** ê¢â¬â Recomendado para rodar 3 engines em paralelo com Ollama local
- **qwen2.5:72b** ê¢â¬â Melhor qualidade mas causa timeout com 3 engines simultêÂ¢neos
- Pode usar qualquer API compatêÂ­vel com formato OpenAI (GPT-4o, Claude, DeepSeek, etc.)

### Uso

1. Acesse **http://localhost:5000**
2. Clique no êÂ­cone de **engrenagem** (configuraêÂ§êÂµes)
3. Clique em **"Salvar e iniciar sistema"** (nêÂ£o apenas "Salvar")
4. Aguarde os 3 engines iniciarem (~30 segundos)
5. Digite sua consulta na caixa de texto e envie
6. Aguarde o processamento (5-30 min dependendo do modelo)
7. O relatêÂ³rio serêÂ¡ gerado automaticamente em HTML/PDF

### Painel de Fontes de NotêÂ­cias
- Na engrenagem, role atêÂ© "Fontes de NotêÂ­cias"
- Ative/desative regiêÂµes (Brasil, EUA, Europa, AmêÂ©rica do Sul)
- Clique "Atualizar NotêÂ­cias" para coletar RSS

### Portas

| Porta | ServiêÂ§o |
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
| GeraêÂ§êÂ£o de relatêÂ³rios HTML/PDF | Funciona |
| Coleta de notêÂ­cias RSS (24 fontes) | Funciona |
| AnêÂ¡lise de sentimento em portuguêÂªs | Funciona |
| Interface web em portuguêÂªs | Funciona |
| LLM via Ollama local | Funciona |

---

## 5. O que ainda nêÂ£o funciona (Fase 4 ê¢â¬â Pendente)

| Recurso | Motivo |
|---------|--------|
| Coleta de posts do Twitter/X, Instagram, Reddit, YouTube | Crawlers nêÂ£o implementados |
| Coleta de comentêÂ¡rios de redes sociais | Sem crawler para plataformas ocidentais |
| AnêÂ¡lise de volume estatêÂ­stico massivo | InsightEngine depende de dados coletados |
| ComparaêÂ§êÂ£o entre plataformas | Sem dados de mêÂºltiplas redes |

### Plano da Fase 4 ê¢â¬â Crawlers Ocidentais

Abordagem hêÂ­brida: **Apify + APIs oficiais** (~6 dias, ~$540/mêÂªs)

| Plataforma | Ferramenta | Custo/mêÂªs |
|-----------|-----------|----------|
| Reddit | PRAW (API oficial) | $0 |
| YouTube | Google API v3 | $0 |
| Twitter/X | Apify (Tweet Scraper) | ~$60 |
| Instagram | Apify (Instagram Scraper) | ~$225 |
| TikTok | Apify (TikTok Scraper) | ~$255 |

Firecrawl foi descartado (bloqueia redes sociais). LinkedIn nêÂ£o recomendado (risco legal).

---

## 6. Problemas conhecidos e soluêÂ§êÂµes

| Problema | SoluêÂ§êÂ£o |
|----------|---------|
| `host.docker.internal` nêÂ£o resolve no Linux | Adicionado `extra_hosts: host.docker.internal:host-gateway` no docker-compose.yml |
| MediaEngine exigia Bocha API | Adicionado suporte a TavilyAPI no Streamlit app e config |
| Timeout com qwen2.5:72b (3 engines paralelos) | Usar qwen2.5:32b + LLM_REQUEST_TIMEOUT=3600 |
| Interface mostra mensagens antigas apêÂ³s restart | Recarregar pêÂ¡gina (F5) |
| Logs em chinêÂªs no container | Rebuildar imagem com `docker compose build` |
| Sistema nêÂ£o aceita consultas | Clicar "Salvar e iniciar sistema" (nêÂ£o apenas "Salvar") |

---

## 7. Estrutura de arquivos modificados

```
BettaFish/
ê¢âÅê¢ââ¬ê¢ââ¬ README.md                    # Traduzido + seêÂ§êÂ£o de infraestrutura
ê¢âÅê¢ââ¬ê¢ââ¬ RELATORIO_PROJETO.md         # Este documento
ê¢âÅê¢ââ¬ê¢ââ¬ .env.example                 # Traduzido
ê¢âÅê¢ââ¬ê¢ââ¬ .dockerignore                # Atualizado (exclui db_data, logs)
ê¢âÅê¢ââ¬ê¢ââ¬ docker-compose.yml           # Build local + extra_hosts + volumes
ê¢âÅê¢ââ¬ê¢ââ¬ config.py                    # TavilyAPI como opêÂ§êÂ£o
ê¢âÅê¢ââ¬ê¢ââ¬ app.py                       # Traduzido + endpoints /api/update-news e /api/news-status
ê¢âÅê¢ââ¬ê¢ââ¬ templates/index.html         # Interface PT-BR + painel de notêÂ­cias
ê¢âÅê¢ââ¬ê¢ââ¬ SingleEngineApp/
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ media_engine_streamlit_app.py   # Suporte TavilyAPI
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ query_engine_streamlit_app.py   # Traduzido
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ insight_engine_streamlit_app.py # Traduzido
ê¢âÅê¢ââ¬ê¢ââ¬ InsightEngine/               # Prompts com plataformas ocidentais
ê¢âÅê¢ââ¬ê¢ââ¬ MediaEngine/                 # TavilyMultimodalSearch adicionado
ê¢âÅê¢ââ¬ê¢ââ¬ QueryEngine/                 # Traduzido
ê¢âÅê¢ââ¬ê¢ââ¬ ReportEngine/                # Traduzido
ê¢âÅê¢ââ¬ê¢ââ¬ ForumEngine/                 # Traduzido
ê¢âÅê¢ââ¬ê¢ââ¬ MindSpider/
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ BroadTopicExtraction/
ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ get_today_news.py    # 24 fontes RSS (BR/USA/EU/LATAM)
ê¢ââê¢ââ¬ê¢ââ¬ SentimentAnalysisModel/      # Modelo multilêÂ­ngue suporta PT
```

---

## 8. Custo de tokens e comparativo de LLMs

Cada relatêÂ³rio completo consome aproximadamente **620.000 tokens** (~430K input + ~190K output) distribuêÂ­dos em ~110-120 chamadas LLM entre os engines.

### DistribuiêÂ§êÂ£o de tokens por componente

| Componente | Chamadas LLM | Tokens estimados |
|-----------|-------------|-----------------|
| InsightEngine | ~32 | ~144.000 |
| QueryEngine | ~32 | ~144.000 |
| MediaEngine | ~32 | ~144.000 |
| ReportEngine | ~15-20 | ~160.000 |
| ForumEngine | ~5-10 | ~30.000 |
| **Total** | **~110-120** | **~620.000** |

### Custo por relatêÂ³rio em APIs comerciais

| Modelo | Custo/relatêÂ³rio | Tempo | Qualidade |
|--------|----------------|-------|-----------|
| Ollama local (qwen2.5:32b) | $0.00 | 3-4 horas | MêÂ©dia |
| DeepSeek Chat | $0.11 | 8-12 min | Boa |
| GPT-4o-mini | $0.17 | 5-8 min | Boa |
| Claude Haiku 3.5 | $1.10 | 8-12 min | Boa |
| GPT-4o | $2.98 | 10-15 min | Muito boa |
| Claude Sonnet 4 | $4.14 | 10-15 min | Excelente |

### ProjeêÂ§êÂ£o de custo mensal (100 relatêÂ³rios/mêÂªs)

| Modelo | Custo mensal |
|--------|-------------|
| Ollama local | $0 (sêÂ³ energia elêÂ©trica) |
| DeepSeek Chat | ~$11 |
| GPT-4o-mini | ~$17 |
| Claude Haiku 3.5 | ~$110 |
| GPT-4o | ~$298 |
| Claude Sonnet 4 | ~$414 |

> **Nota:** Todos os modelos usam formato OpenAI-compatible. Basta trocar `API_KEY`, `BASE_URL` e `MODEL_NAME` no `.env` para alternar entre provedores. Pode usar modelos diferentes por engine (ex: DeepSeek para engines de busca, GPT-4o para o ReportEngine).

---

## 9. RepositêÂ³rio

- **Origem**: [666ghj/BettaFish](https://github.com/666ghj/BettaFish) (chinêÂªs)
- **Fork adaptado**: [linnoff88-dev/BettaFish](https://github.com/linnoff88-dev/BettaFish) (portuguêÂªs brasileiro)
