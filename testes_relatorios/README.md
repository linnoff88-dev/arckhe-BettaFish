# Testes de Relatórios — BettaFish BR

Histórico de testes realizados durante a portaçêo do sistema para o mercado brasileiro.

## Teste 01 — InsightEngine com banco vazio (2026-03-22)

**Arquivo:** `teste_01_insight_only_banco_vazio.md`

**Consulta:** "O futuro tende a valorizar menos quem apenas executa tarefas e mais quem cria oportunidades e quem orquestra resultados com apoio de IA, automaçêo e tecnologia..."

**Configuraçêo:**
- Modelo: qwen2.5:32b (Ollama local)
- Timeout: 3600s
- Busca: Tavily (configurado mas nêo usado pelo InsightEngine)

**Engines que rodaram:**
| Engine | Status |
|--------|--------|
| InsightEngine | Completou (banco vazio — dados genéricos gerados pelo LLM) |
| QueryEngine | Nêo recebeu a consulta |
| MediaEngine | Nêo recebeu a consulta |

**Resultado:** Relatório de 5 capítulos gerado, porém com dados inventados pelo LLM (Twitter 30mil, LinkedIn 45mil sêo fictícios). O InsightEngine nêo encontrou dados reais no PostgreSQL porque o banco está vazio — sem coleta prévia do MindSpider.

**Conclusêo:** O InsightEngine funciona end-to-end, mas precisa de dados no banco para gerar relatórios com informações reais. Para resultados úteis, é necessário que o QueryEngine (Tavily) e MediaEngine também processem a consulta.

**Problemas encontrados nesta sessêo:**
1. `host.docker.internal` nêo resolvia no Linux → corrigido com `extra_hosts`
2. MediaEngine exigia Bocha API → corrigido com suporte a TavilyAPI
3. `config.py` nêo aceitava `TavilyAPI` no Literal → corrigido
4. `media_engine_streamlit_app.py` nêo roteava TavilyAPI → corrigido
5. qwen2.5:72b causava timeout com 3 engines paralelos → trocado para qwen2.5:32b

---

## Teste 02 — 3 Engines completos com Tavily (2026-03-22)

**Arquivos:**
- `teste_02_query_engine_tavily.md` (8.2K)
- `teste_02_media_engine_tavily.md` (1.8K)
- `teste_02_insight_engine.md` (8.0K)

**Consulta:** "O futuro tende a valorizar menos quem apenas executa tarefas e mais quem cria oportunidades e quem orquestra resultados com apoio de IA, automaçêo e tecnologia..."

**Configuraçêo:**
- Modelo: qwen2.5:32b (Ollama local)
- Timeout: 3600s
- Busca: TavilyAPI
- `.env`: SEARCH_TOOL_TYPE=TavilyAPI

**Engines que rodaram:**
| Engine | Status | Duraçêo | Tamanho |
|--------|--------|---------|---------|
| QueryEngine | Concluído com Tavily | ~1h40min | 8.2K |
| MediaEngine | Concluído (Bocha falhou 401, continuou sem busca) | ~1h10min | 1.8K |
| InsightEngine | Concluído (banco vazio, dados genéricos) | ~1h25min | 8.0K |

**Resultado:** Primeiro teste com os 3 engines processando em paralelo. QueryEngine trouxe dados reais via Tavily sobre IA na educaçêo brasileira. MediaEngine tentou usar Bocha (erro 401) mas completou com conteúdo reduzido. InsightEngine gerou conteúdo sem dados reais (banco vazio).

**Problemas encontrados:**
1. Interface sobrescrevia `SEARCH_TOOL_TYPE=BochaAPI` ao salvar → corrigido adicionando `TavilyAPI` ao dropdown
2. Chave Tavily estava duplicada no `.env` → corrigido
3. MediaEngine ainda tentou Bocha apesar do `.env` estar com TavilyAPI → o `DeepSearchAgent` do MediaEngine usa `load_agent_from_config()` que prioriza Bocha se ambas chaves existirem

**Conclusêo:** O sistema funciona end-to-end com os 3 engines. O QueryEngine com Tavily é o que traz mais valor. O MediaEngine precisa de ajuste para usar Tavily consistentemente.
