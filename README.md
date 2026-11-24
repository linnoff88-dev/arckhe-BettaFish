<div align="center">

<img src="static/image/logo_compressed.png" alt="BettaFish Logo" width="100%">

<a href="https://trendshift.io/repositories/15286" target="_blank"><img src="https://trendshift.io/api/badge/repositories/15286" alt="666ghj%2FBettaFish | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

<a href="https://aihubmix.com/?aff=8Ds9" target="_blank"><img src="./static/image/logo_aihubmix.png" alt="666ghj%2FBettaFish | Trendshift" height="40"/></a>&ensp;
<a href="https://open.anspire.cn/?share_code=3E1FUOUH" target="_blank"><img src="./static/image/logo_anspire.png" alt="666ghj%2FBettaFish | Trendshift" height="40"/></a>

[![GitHub Stars](https://img.shields.io/github/stars/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/stargazers)
[![GitHub Watchers](https://img.shields.io/github/watchers/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/watchers)
[![GitHub Forks](https://img.shields.io/github/forks/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/network)
[![GitHub Issues](https://img.shields.io/github/issues/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/pulls)

[![GitHub License](https://img.shields.io/github/license/666ghj/BettaFish?style=flat-square)](https://github.com/666ghj/BettaFish/blob/main/LICENSE)
[![Version](https://img.shields.io/badge/version-v1.2.1-green.svg?style=flat-square)](https://github.com/666ghj/BettaFish)
[![Docker](https://img.shields.io/badge/Docker-Build-2496ED?style=flat-square&logo=docker&logoColor=white)](https://hub.docker.com/)



[English](./README-EN.md) | [PortuguÃªs](./README.md)

</div>

> [!NOTE]
> ### Fork BR/LATAM â€” Adaptado para o mercado brasileiro e latino-americano
>
> | Documento | DescriÃ§Ã£o |
> |-----------|-----------|
> | [RelatÃ³rio Completo do Projeto](./RELATORIO_PROJETO.md) | Tudo sobre o que foi feito, arquitetura, configuraÃ§Ã£o, uso e plano de evoluÃ§Ã£o |
> | [ConfiguraÃ§Ã£o RÃ¡pida](#%EF%B8%8F-infraestrutura-para-deploy) | Como subir o sistema com Docker + Ollama |
> | [.env.example](./.env.example) | Modelo de configuraÃ§Ã£o com todas as variÃ¡veis documentadas |
>
> **Destaques desta versÃ£o:**
> - Interface, logs e prompts 100% em portuguÃªs
> - Busca web global via Tavily (substituindo APIs chinesas)
> - 24 fontes de notÃ­cias RSS (Brasil, EUA, Europa, AmÃ©rica do Sul)
> - AnÃ¡lise de sentimento multilÃ­ngue com suporte nativo a portuguÃªs
> - Docker local com Ollama (sem dependÃªncia de APIs pagas de LLM)

> [!IMPORTANT]
> Confira nosso motor de previsÃ£o recÃ©m-lanÃ§ado: [MiroFish - Motor de inteligÃªncia coletiva simples e universal para prever tudo](https://github.com/666ghj/MiroFish)
>
> <img src="static/image/MiroFish_logo_compressed.jpeg" alt="banner" width="300">
>
> "Os trÃªs pilares da anÃ¡lise de dados" estÃ£o totalmente integrados: temos a alegria de anunciar o lanÃ§amento oficial do MiroFish! Com a Ãºltima peÃ§a do quebra-cabeÃ§a encaixada, construÃ­mos o fluxo completo do BettaFish (coleta e anÃ¡lise de dados) ao MiroFish (previsÃ£o panorÃ¢mica). Assim, o ciclo completo dos dados brutos Ã  tomada de decisÃ£o inteligente estÃ¡ concluÃ­do, tornando possÃ­vel prever o futuro!

## âš¡ VisÃ£o Geral do Projeto

"**WeiYu**" (Micro-OpiniÃ£o) Ã© um sistema inovador de anÃ¡lise de opiniÃ£o pÃºblica baseado em multi-agentes, desenvolvido do zero, que ajuda os usuÃ¡rios a romper bolhas informacionais, restaurar o panorama real da opiniÃ£o pÃºblica, prever tendÃªncias futuras e auxiliar na tomada de decisÃµes. O usuÃ¡rio sÃ³ precisa expressar sua necessidade de anÃ¡lise como em uma conversa, e os agentes iniciam automaticamente a anÃ¡lise de mais de 30 plataformas de mÃ­dia social nacionais e internacionais e de milhÃµes de comentÃ¡rios do pÃºblico.

> "WeiYu" Ã© um trocadilho em chinÃªs que soa como "peixinho". BettaFish Ã© um peixe de corpo muito pequeno, mas extremamente combativo e bonito, simbolizando "pequeno mas poderoso, sem medo de desafios"

Veja o relatÃ³rio de pesquisa gerado pelo sistema usando "opiniÃ£o pÃºblica da Universidade de Wuhan" como exemplo: [RelatÃ³rio de AnÃ¡lise Aprofundada da ReputaÃ§Ã£o da Marca da Universidade de Wuhan](./final_reports/final_report__20250827_131630.html)

Veja o vÃ­deo de uma execuÃ§Ã£o completa do sistema usando "opiniÃ£o pÃºblica da Universidade de Wuhan" como exemplo: [VÃ­deo - RelatÃ³rio de AnÃ¡lise Aprofundada da ReputaÃ§Ã£o da Marca da Universidade de Wuhan](https://www.bilibili.com/video/BV1TH1WBxEWN/?vd_source=da3512187e242ce17dceee4c537ec7a6#reply279744466833)

NÃ£o apenas na qualidade dos relatÃ³rios, mas em comparaÃ§Ã£o com produtos similares, possuÃ­mos 6 grandes vantagens:

1. **Monitoramento Global Impulsionado por IA**: Clusters de crawlers de IA operando 24/7, cobrindo integralmente mais de 10 plataformas de mÃ­dia social nacionais e internacionais como Weibo, Xiaohongshu, Douyin, Kuaishou, etc. AlÃ©m de capturar conteÃºdo em alta em tempo real, consegue aprofundar-se em comentÃ¡rios massivos de usuÃ¡rios, permitindo ouvir a voz mais autÃªntica e abrangente do pÃºblico.

2. **Motor de AnÃ¡lise Composto que Vai AlÃ©m dos LLMs**: NÃ£o dependemos apenas dos 5 tipos de Agents profissionais projetados, mas tambÃ©m integramos middlewares como modelos ajustados finamente e modelos estatÃ­sticos. AtravÃ©s da colaboraÃ§Ã£o multi-modelo, garantimos profundidade, precisÃ£o e perspectivas multidimensionais nos resultados da anÃ¡lise.

3. **Poderosa Capacidade Multimodal**: Rompendo as limitaÃ§Ãµes de texto e imagem, consegue analisar em profundidade conteÃºdo de vÃ­deos curtos do Douyin, Kuaishou, entre outros, e extrair com precisÃ£o cartÃµes de informaÃ§Ã£o multimodal estruturada como clima, calendÃ¡rio e aÃ§Ãµes de motores de busca modernos, permitindo domÃ­nio completo das dinÃ¢micas de opiniÃ£o pÃºblica.

4. **Mecanismo de ColaboraÃ§Ã£o "FÃ³rum" entre Agents**: Atribuindo a cada Agent um conjunto Ãºnico de ferramentas e modos de pensamento, introduzimos um modelo de moderador de debates, permitindo colisÃ£o e debate de cadeias de pensamento atravÃ©s do mecanismo de "FÃ³rum". Isso nÃ£o apenas evita limitaÃ§Ãµes de pensamento de um Ãºnico modelo e a homogeneizaÃ§Ã£o causada pela comunicaÃ§Ã£o, mas tambÃ©m gera inteligÃªncia coletiva e suporte Ã  decisÃ£o de maior qualidade.

5. **IntegraÃ§Ã£o Perfeita de Dados PÃºblicos e Privados**: A plataforma nÃ£o apenas analisa a opiniÃ£o pÃºblica aberta, mas tambÃ©m fornece interfaces de alta seguranÃ§a, permitindo integrar perfeitamente bancos de dados internos de negÃ³cios com dados de opiniÃ£o pÃºblica. Quebrando barreiras de dados, oferece poderosa capacidade de anÃ¡lise de "tendÃªncias externas + insights internos" para negÃ³cios verticais.

6. **Framework Leve e Altamente ExtensÃ­vel**: Baseado em design modular em Python puro, alcanÃ§a implantaÃ§Ã£o leve e com um Ãºnico clique. A estrutura do cÃ³digo Ã© clara, e desenvolvedores podem facilmente integrar modelos personalizados e lÃ³gica de negÃ³cios, permitindo expansÃ£o rÃ¡pida e personalizaÃ§Ã£o profunda da plataforma.

**ComeÃ§a pela opiniÃ£o pÃºblica, mas nÃ£o se limita a ela**. O objetivo do "WeiYu" Ã© tornar-se um motor de anÃ¡lise de dados simples e universal que impulsiona qualquer cenÃ¡rio de negÃ³cio.

> Por exemplo, vocÃª sÃ³ precisa modificar os parÃ¢metros de API e prompts do conjunto de ferramentas do Agent para transformÃ¡-lo em um sistema de anÃ¡lise de mercado no setor financeiro
>
> Segue um tÃ³pico de discussÃ£o bastante ativo no fÃ³rum L: https://linux.do/t/topic/1009280
>
> Veja a avaliaÃ§Ã£o feita por um membro do fÃ³rum L [ComparaÃ§Ã£o do projeto open source (WeiYu) com manus|minimax|ChatGPT|Perplexity](https://linux.do/t/topic/1148040)

<div align="center">
<img src="static/image/system_schematic.png" alt="banner" width="800">

Diga adeus aos painÃ©is de dados tradicionais. No "WeiYu", tudo comeÃ§a com uma simples pergunta - vocÃª sÃ³ precisa expressar sua necessidade de anÃ¡lise como em uma conversa
</div>

## ðŸª„ Patrocinadores

PatrocÃ­nio de API de modelos LLM: <a href="https://aihubmix.com/?aff=8Ds9" target="_blank"><img src="./static/image/logo_aihubmix.png" alt="666ghj%2FBettaFish | Trendshift" height="40"/></a>

<details>
<summary>Provedor de capacidades centrais de agentes inteligentes como busca conectada por IA, anÃ¡lise de arquivos e captura de conteÃºdo web:</a><span style="margin-left: 10px"><a href="https://open.anspire.cn/?share_code=3E1FUOUH" target="_blank"><img src="./static/image/logo_anspire.png" alt="666ghj%2FBettaFish | Trendshift" height="50"/></a></summary>
A Plataforma Aberta Anspire (Anspire Open) Ã© um provedor lÃ­der de infraestrutura para a era dos agentes inteligentes. Oferecemos aos desenvolvedores a pilha de capacidades centrais necessÃ¡rias para construir agentes poderosos, com serviÃ§os jÃ¡ disponÃ­veis como busca conectada por IA [mÃºltiplas versÃµes, preÃ§os extremamente competitivos], anÃ¡lise de arquivos [gratuita por tempo limitado] e captura de conteÃºdo web [gratuita por tempo limitado], automaÃ§Ã£o de navegador em nuvem (Anspire Browser Agent) [em beta], reescrita em mÃºltiplas rodadas e mais, fornecendo continuamente uma base sÃ³lida para que agentes inteligentes se conectem e operem no complexo mundo digital. IntegraÃ§Ã£o perfeita com plataformas de agentes populares como Dify, Coze, Yuanqi, entre outras. AtravÃ©s de um sistema de cobranÃ§a transparente por pontos e design modular, oferecemos suporte personalizado eficiente e de baixo custo para empresas, acelerando o processo de modernizaÃ§Ã£o inteligente.
</details>

## ðŸ—ï¸ Arquitetura do Sistema

### Diagrama da Arquitetura Geral

**Insight Agent** MineraÃ§Ã£o de banco de dados privado: Agente de IA para anÃ¡lise aprofundada de bancos de dados privados de opiniÃ£o pÃºblica

**Media Agent** AnÃ¡lise de conteÃºdo multimodal: Agente de IA com poderosas capacidades multimodais

**Query Agent** Busca precisa de informaÃ§Ãµes: Agente de IA com capacidade de busca web nacional e internacional

**Report Agent** GeraÃ§Ã£o inteligente de relatÃ³rios: Agente de IA para geraÃ§Ã£o de relatÃ³rios em mÃºltiplas rodadas com templates integrados

<div align="center">
<img src="static/image/framework.png" alt="banner" width="800">
</div>

### Fluxo Completo de Uma AnÃ¡lise

| Etapa | Nome da Fase | OperaÃ§Ã£o Principal | Componentes Envolvidos | CaracterÃ­sticas de Loop |
|------|----------|----------|----------|----------|
| 1 | Pergunta do UsuÃ¡rio | AplicaÃ§Ã£o principal Flask recebe a consulta | AplicaÃ§Ã£o principal Flask | - |
| 2 | InicializaÃ§Ã£o Paralela | TrÃªs Agents comeÃ§am a trabalhar simultaneamente | Query Agent, Media Agent, Insight Agent | - |
| 3 | AnÃ¡lise Preliminar | Cada Agent usa suas ferramentas exclusivas para busca geral | Cada Agent + conjunto de ferramentas exclusivo | - |
| 4 | FormulaÃ§Ã£o de EstratÃ©gia | FormulaÃ§Ã£o de estratÃ©gia de pesquisa segmentada com base nos resultados preliminares | MÃ³dulo de decisÃ£o interno de cada Agent | - |
| 5-N | **Fase de Loop** | **ColaboraÃ§Ã£o no FÃ³rum + Pesquisa Aprofundada** | **ForumEngine + Todos os Agents** | **Loop em mÃºltiplas rodadas** |
| 5.1 | Pesquisa Aprofundada | Cada Agent realiza busca especializada guiado pelo moderador do fÃ³rum | Cada Agent + mecanismo de reflexÃ£o + orientaÃ§Ã£o do fÃ³rum | Cada rodada do loop |
| 5.2 | ColaboraÃ§Ã£o no FÃ³rum | ForumEngine monitora falas dos Agents e gera orientaÃ§Ã£o do moderador | ForumEngine + LLM moderador | Cada rodada do loop |
| 5.3 | Troca e FusÃ£o | Cada Agent ajusta sua direÃ§Ã£o de pesquisa com base na discussÃ£o | Cada Agent + ferramenta forum_reader | Cada rodada do loop |
| N+1 | IntegraÃ§Ã£o de Resultados | Report Agent coleta todos os resultados de anÃ¡lise e conteÃºdo do fÃ³rum | Report Agent | - |
| N+2 | RepresentaÃ§Ã£o IntermediÃ¡ria IR | SeleÃ§Ã£o dinÃ¢mica de template e estilo, geraÃ§Ã£o de metadados em mÃºltiplas rodadas, montagem em representaÃ§Ã£o intermediÃ¡ria IR | Report Agent + motor de templates | - |
| N+3 | GeraÃ§Ã£o do RelatÃ³rio | VerificaÃ§Ã£o de qualidade por blocos, renderizaÃ§Ã£o em relatÃ³rio HTML interativo baseado em IR | Report Agent + motor de montagem | - |

### Estrutura de CÃ³digo do Projeto

```
BettaFish/
â”œâ”€â”€ QueryEngine/                            # Agent de busca ampla de notÃ­cias nacionais e internacionais
â”‚   â”œâ”€â”€ agent.py                            # LÃ³gica principal do Agent, coordena fluxo de busca e anÃ¡lise
â”‚   â”œâ”€â”€ llms/                               # Encapsulamento de interface LLM
â”‚   â”œâ”€â”€ nodes/                              # NÃ³s de processamento: busca, formataÃ§Ã£o, resumo, etc.
â”‚   â”œâ”€â”€ tools/                              # Conjunto de ferramentas de busca de notÃ­cias nacionais e internacionais
â”‚   â”œâ”€â”€ utils/                              # FunÃ§Ãµes utilitÃ¡rias
â”‚   â”œâ”€â”€ state/                              # Gerenciamento de estado
â”‚   â”œâ”€â”€ prompts/                            # Templates de prompts
â”‚   â””â”€â”€ ...
â”œâ”€â”€ MediaEngine/                            # Agent de compreensÃ£o multimodal poderoso
â”‚   â”œâ”€â”€ agent.py                            # LÃ³gica principal do Agent, processa conteÃºdo multimodal como vÃ­deo/imagem
â”‚   â”œâ”€â”€ llms/                               # Encapsulamento de interface LLM
â”‚   â”œâ”€â”€ nodes/                              # NÃ³s de processamento: busca, formataÃ§Ã£o, resumo, etc.
â”‚   â”œâ”€â”€ tools/                              # Conjunto de ferramentas de busca multimodal
â”‚   â”œâ”€â”€ utils/                              # FunÃ§Ãµes utilitÃ¡rias
â”‚   â”œâ”€â”€ state/                              # Gerenciamento de estado
â”‚   â”œâ”€â”€ prompts/                            # Templates de prompts
â”‚   â””â”€â”€ ...
â”œâ”€â”€ InsightEngine/                          # Agent de mineraÃ§Ã£o de banco de dados privado
â”‚   â”œâ”€â”€ agent.py                            # LÃ³gica principal do Agent, coordena consulta e anÃ¡lise do banco de dados
â”‚   â”œâ”€â”€ llms/                               # Encapsulamento de interface LLM
â”‚   â”‚   â””â”€â”€ base.py                         # Cliente unificado compatÃ­vel com OpenAI
â”‚   â”œâ”€â”€ nodes/                              # NÃ³s de processamento: busca, formataÃ§Ã£o, resumo, etc.
â”‚   â”‚   â”œâ”€â”€ base_node.py                    # Classe base de nÃ³
â”‚   â”‚   â”œâ”€â”€ search_node.py                  # NÃ³ de busca
â”‚   â”‚   â”œâ”€â”€ formatting_node.py              # NÃ³ de formataÃ§Ã£o
â”‚   â”‚   â”œâ”€â”€ report_structure_node.py        # NÃ³ de estrutura de relatÃ³rio
â”‚   â”‚   â””â”€â”€ summary_node.py                 # NÃ³ de resumo
â”‚   â”œâ”€â”€ tools/                              # Conjunto de ferramentas de consulta e anÃ¡lise de banco de dados
â”‚   â”‚   â”œâ”€â”€ keyword_optimizer.py            # Middleware de otimizaÃ§Ã£o de palavras-chave Qwen
â”‚   â”‚   â”œâ”€â”€ search.py                       # Conjunto de ferramentas de operaÃ§Ã£o de banco de dados (busca de tÃ³picos, obtenÃ§Ã£o de comentÃ¡rios, etc.)
â”‚   â”‚   â””â”€â”€ sentiment_analyzer.py           # Ferramenta integrada de anÃ¡lise de sentimento
â”‚   â”œâ”€â”€ utils/                              # FunÃ§Ãµes utilitÃ¡rias
â”‚   â”‚   â”œâ”€â”€ config.py                       # Gerenciamento de configuraÃ§Ã£o
â”‚   â”‚   â”œâ”€â”€ db.py                           # Motor assÃ­ncrono SQLAlchemy e encapsulamento de consulta somente leitura
â”‚   â”‚   â””â”€â”€ text_processing.py              # Ferramentas de processamento de texto
â”‚   â”œâ”€â”€ state/                              # Gerenciamento de estado
â”‚   â”‚   â””â”€â”€ state.py                        # DefiniÃ§Ã£o de estado do Agent
â”‚   â”œâ”€â”€ prompts/                            # Templates de prompts
â”‚   â”‚   â””â”€â”€ prompts.py                      # Diversos prompts
â”‚   â””â”€â”€ __init__.py
â”œâ”€â”€ ReportEngine/                           # Agent de geraÃ§Ã£o de relatÃ³rios em mÃºltiplas rodadas
â”‚   â”œâ”€â”€ agent.py                            # Orquestrador geral: seleÃ§Ã£o de templateâ†’layoutâ†’extensÃ£oâ†’capÃ­tulosâ†’renderizaÃ§Ã£o
â”‚   â”œâ”€â”€ flask_interface.py                  # Entrada Flask/SSE, gerencia fila de tarefas e eventos de streaming
â”‚   â”œâ”€â”€ llms/                               # Encapsulamento de LLM compatÃ­vel com OpenAI
â”‚   â”‚   â””â”€â”€ base.py                         # Cliente unificado com streaming/retry
â”‚   â”œâ”€â”€ core/                               # Funcionalidades centrais: parsing de template, armazenamento de capÃ­tulos, montagem de documento
â”‚   â”‚   â”œâ”€â”€ template_parser.py              # Fatiamento de template Markdown e geraÃ§Ã£o de slug
â”‚   â”‚   â”œâ”€â”€ chapter_storage.py              # DiretÃ³rio run de capÃ­tulos, manifest e escrita de fluxo raw
â”‚   â”‚   â””â”€â”€ stitcher.py                     # Montador de Document IR, preenchimento de Ã¢ncoras/metadados
â”‚   â”œâ”€â”€ ir/                                 # Contrato e validaÃ§Ã£o de RepresentaÃ§Ã£o IntermediÃ¡ria (IR) do relatÃ³rio
â”‚   â”‚   â”œâ”€â”€ schema.py                       # DefiniÃ§Ã£o de constantes de Schema de blocos/marcadores
â”‚   â”‚   â””â”€â”€ validator.py                    # Validador de estrutura JSON de capÃ­tulos
â”‚   â”œâ”€â”€ nodes/                              # NÃ³s de inferÃªncia do fluxo completo
â”‚   â”‚   â”œâ”€â”€ base_node.py                    # Classe base de nÃ³ + hooks de log/estado
â”‚   â”‚   â”œâ”€â”€ template_selection_node.py      # Coleta de candidatos de template e seleÃ§Ã£o por LLM
â”‚   â”‚   â”œâ”€â”€ document_layout_node.py         # Design de tÃ­tulo/Ã­ndice/tema
â”‚   â”‚   â”œâ”€â”€ word_budget_node.py             # Planejamento de extensÃ£o e geraÃ§Ã£o de instruÃ§Ãµes por capÃ­tulo
â”‚   â”‚   â””â”€â”€ chapter_generation_node.py      # GeraÃ§Ã£o JSON por capÃ­tulo + validaÃ§Ã£o
â”‚   â”œâ”€â”€ prompts/                            # Biblioteca de prompts e descriÃ§Ãµes de Schema
â”‚   â”‚   â””â”€â”€ prompts.py                      # Prompts de seleÃ§Ã£o de template/layout/extensÃ£o/capÃ­tulo
â”‚   â”œâ”€â”€ renderers/                          # Renderizadores de IR
â”‚   â”‚   â”œâ”€â”€ html_renderer.py               # Document IRâ†’HTML interativo
â”‚   â”‚   â”œâ”€â”€ pdf_renderer.py                # HTMLâ†’exportaÃ§Ã£o PDF (WeasyPrint)
â”‚   â”‚   â”œâ”€â”€ pdf_layout_optimizer.py         # Otimizador de layout PDF
â”‚   â”‚   â””â”€â”€ chart_to_svg.py                # Ferramenta de conversÃ£o de grÃ¡ficos para SVG
â”‚   â”œâ”€â”€ state/                              # Modelos de estado de tarefa/metadados
â”‚   â”‚   â””â”€â”€ state.py                        # ReportState e ferramentas de serializaÃ§Ã£o
â”‚   â”œâ”€â”€ utils/                              # ConfiguraÃ§Ã£o e ferramentas auxiliares
â”‚   â”‚   â”œâ”€â”€ config.py                       # Pydantic Settings e auxiliar de impressÃ£o
â”‚   â”‚   â”œâ”€â”€ dependency_check.py             # Ferramenta de verificaÃ§Ã£o de dependÃªncias
â”‚   â”‚   â”œâ”€â”€ json_parser.py                  # Ferramenta de parsing JSON
â”‚   â”‚   â”œâ”€â”€ chart_validator.py              # Ferramenta de validaÃ§Ã£o de grÃ¡ficos
â”‚   â”‚   â””â”€â”€ chart_repair_api.py             # API de reparo de grÃ¡ficos
â”‚   â”œâ”€â”€ report_template/                    # Biblioteca de templates Markdown
â”‚   â”‚   â”œâ”€â”€ ä¼ä¸šå“ç‰Œå£°èª‰åˆ†æžæŠ¥å‘Š.md
â”‚   â”‚   â””â”€â”€ ...
â”‚   â””â”€â”€ __init__.py
â”œâ”€â”€ ForumEngine/                            # Motor de fÃ³rum: mecanismo de colaboraÃ§Ã£o entre Agents
â”‚   â”œâ”€â”€ monitor.py                          # NÃºcleo de monitoramento de logs e gerenciamento do fÃ³rum
â”‚   â”œâ”€â”€ llm_host.py                         # MÃ³dulo LLM do moderador do fÃ³rum
â”‚   â””â”€â”€ __init__.py
â”œâ”€â”€ MindSpider/                             # Sistema de crawlers de mÃ­dias sociais
â”‚   â”œâ”€â”€ main.py                             # Ponto de entrada principal do crawler
â”‚   â”œâ”€â”€ config.py                           # Arquivo de configuraÃ§Ã£o do crawler
â”‚   â”œâ”€â”€ BroadTopicExtraction/               # MÃ³dulo de extraÃ§Ã£o de tÃ³picos
â”‚   â”‚   â”œâ”€â”€ main.py                         # Programa principal de extraÃ§Ã£o de tÃ³picos
â”‚   â”‚   â”œâ”€â”€ database_manager.py             # Gerenciador de banco de dados
â”‚   â”‚   â”œâ”€â”€ get_today_news.py               # ObtenÃ§Ã£o de notÃ­cias do dia
â”‚   â”‚   â””â”€â”€ topic_extractor.py              # Extrator de tÃ³picos
â”‚   â”œâ”€â”€ DeepSentimentCrawling/              # MÃ³dulo de crawling profundo de opiniÃ£o pÃºblica
â”‚   â”‚   â”œâ”€â”€ main.py                         # Programa principal de crawling profundo
â”‚   â”‚   â”œâ”€â”€ keyword_manager.py              # Gerenciador de palavras-chave
â”‚   â”‚   â”œâ”€â”€ platform_crawler.py             # Gerenciador de crawlers por plataforma
â”‚   â”‚   â””â”€â”€ MediaCrawler/                   # NÃºcleo de crawlers de mÃ­dias sociais
â”‚   â”‚       â”œâ”€â”€ main.py
â”‚   â”‚       â”œâ”€â”€ config/                     # ConfiguraÃ§Ãµes por plataforma
â”‚   â”‚       â”œâ”€â”€ media_platform/             # ImplementaÃ§Ã£o de crawlers por plataforma
â”‚   â”‚       â””â”€â”€ ...
â”‚   â””â”€â”€ schema/                             # DefiniÃ§Ã£o de estrutura do banco de dados
â”‚       â”œâ”€â”€ db_manager.py                   # Gerenciador de banco de dados
â”‚       â”œâ”€â”€ init_database.py                # Script de inicializaÃ§Ã£o do banco de dados
â”‚       â”œâ”€â”€ mindspider_tables.sql           # SQL da estrutura de tabelas do banco de dados
â”‚       â”œâ”€â”€ models_bigdata.py               # Mapeamento SQLAlchemy das tabelas de opiniÃ£o pÃºblica em larga escala
â”‚       â””â”€â”€ models_sa.py                    # Modelos ORM de tabelas estendidas DailyTopic/Task
â”œâ”€â”€ SentimentAnalysisModel/                 # ColeÃ§Ã£o de modelos de anÃ¡lise de sentimento
â”‚   â”œâ”€â”€ WeiboSentiment_Finetuned/           # Modelos BERT/GPT-2 ajustados finamente
â”‚   â”‚   â”œâ”€â”€ BertChinese-Lora/               # Ajuste fino LoRA do BERT chinÃªs
â”‚   â”‚   â”‚   â”œâ”€â”€ train.py
â”‚   â”‚   â”‚   â”œâ”€â”€ predict.py
â”‚   â”‚   â”‚   â””â”€â”€ ...
â”‚   â”‚   â””â”€â”€ GPT2-Lora/                      # Ajuste fino LoRA do GPT-2
â”‚   â”‚       â”œâ”€â”€ train.py
â”‚   â”‚       â”œâ”€â”€ predict.py
â”‚   â”‚       â””â”€â”€ ...
â”‚   â”œâ”€â”€ WeiboMultilingualSentiment/         # AnÃ¡lise de sentimento multilÃ­ngue
â”‚   â”‚   â”œâ”€â”€ train.py
â”‚   â”‚   â”œâ”€â”€ predict.py
â”‚   â”‚   â””â”€â”€ ...
â”‚   â”œâ”€â”€ WeiboSentiment_SmallQwen/           # Ajuste fino do Qwen3 com poucos parÃ¢metros
â”‚   â”‚   â”œâ”€â”€ train.py
â”‚   â”‚   â”œâ”€â”€ predict_universal.py
â”‚   â”‚   â””â”€â”€ ...
â”‚   â””â”€â”€ WeiboSentiment_MachineLearning/     # MÃ©todos tradicionais de aprendizado de mÃ¡quina
â”‚       â”œâ”€â”€ train.py
â”‚       â”œâ”€â”€ predict.py
â”‚       â””â”€â”€ ...
â”œâ”€â”€ SingleEngineApp/                        # AplicaÃ§Ãµes Streamlit de Agents individuais
â”‚   â”œâ”€â”€ query_engine_streamlit_app.py       # AplicaÃ§Ã£o independente do QueryEngine
â”‚   â”œâ”€â”€ media_engine_streamlit_app.py       # AplicaÃ§Ã£o independente do MediaEngine
â”‚   â””â”€â”€ insight_engine_streamlit_app.py     # AplicaÃ§Ã£o independente do InsightEngine
â”œâ”€â”€ query_engine_streamlit_reports/         # SaÃ­da da aplicaÃ§Ã£o individual do QueryEngine
â”œâ”€â”€ media_engine_streamlit_reports/         # SaÃ­da da aplicaÃ§Ã£o individual do MediaEngine
â”œâ”€â”€ insight_engine_streamlit_reports/       # SaÃ­da da aplicaÃ§Ã£o individual do InsightEngine
â”œâ”€â”€ templates/                              # Templates do frontend Flask
â”‚   â””â”€â”€ index.html                          # HTML da interface principal
â”œâ”€â”€ static/                                 # Recursos estÃ¡ticos
â”‚   â”œâ”€â”€ image/                              # Recursos de imagem
â”‚   â”‚   â””â”€â”€ ...
â”‚   â”œâ”€â”€ Partial README for PDF Exporting/   # InstruÃ§Ãµes de configuraÃ§Ã£o de dependÃªncias para exportaÃ§Ã£o PDF
â”‚   â””â”€â”€ v2_report_example/                  # Exemplos de renderizaÃ§Ã£o de relatÃ³rios
â”‚       â””â”€â”€ report_all_blocks_demo/         # DemonstraÃ§Ã£o de todos os tipos de blocos (HTML/PDF/MD)
â”œâ”€â”€ logs/                                   # DiretÃ³rio de logs de execuÃ§Ã£o
â”œâ”€â”€ final_reports/                          # Arquivos de relatÃ³rios finais gerados
â”‚   â”œâ”€â”€ ir/                                 # Arquivos JSON de IR do relatÃ³rio
â”‚   â””â”€â”€ *.html                              # RelatÃ³rios HTML finais
â”œâ”€â”€ utils/                                  # FunÃ§Ãµes utilitÃ¡rias gerais
â”‚   â”œâ”€â”€ forum_reader.py                     # Ferramenta de comunicaÃ§Ã£o do fÃ³rum entre Agents
â”‚   â”œâ”€â”€ github_issues.py                    # GeraÃ§Ã£o unificada de links para GitHub Issues e mensagens de erro
â”‚   â””â”€â”€ retry_helper.py                     # Ferramenta de mecanismo de retry para requisiÃ§Ãµes de rede
â”œâ”€â”€ tests/                                  # Testes unitÃ¡rios e de integraÃ§Ã£o
â”‚   â”œâ”€â”€ run_tests.py                        # Script de entrada do pytest
â”‚   â”œâ”€â”€ test_monitor.py                     # Testes unitÃ¡rios do monitoramento do ForumEngine
â”‚   â”œâ”€â”€ test_report_engine_sanitization.py  # Testes de seguranÃ§a do ReportEngine
â”‚   â””â”€â”€ ...
â”œâ”€â”€ app.py                                  # Ponto de entrada da aplicaÃ§Ã£o Flask principal
â”œâ”€â”€ config.py                               # Arquivo de configuraÃ§Ã£o global
â”œâ”€â”€ .env.example                            # Arquivo de exemplo de variÃ¡veis de ambiente
â”œâ”€â”€ docker-compose.yml                      # ConfiguraÃ§Ã£o de orquestraÃ§Ã£o multi-serviÃ§o Docker
â”œâ”€â”€ Dockerfile                              # Arquivo de construÃ§Ã£o de imagem Docker
â”œâ”€â”€ requirements.txt                        # Lista de dependÃªncias Python
â”œâ”€â”€ regenerate_latest_html.py               # Remontagem e renderizaÃ§Ã£o HTML usando os capÃ­tulos mais recentes
â”œâ”€â”€ regenerate_latest_md.py                 # Remontagem e renderizaÃ§Ã£o Markdown usando os capÃ­tulos mais recentes
â”œâ”€â”€ regenerate_latest_pdf.py                # Script de regeneraÃ§Ã£o de PDF
â”œâ”€â”€ report_engine_only.py                   # VersÃ£o de linha de comando do Report Engine
â”œâ”€â”€ README.md                               # DocumentaÃ§Ã£o em portuguÃªs
â”œâ”€â”€ README-EN.md                            # DocumentaÃ§Ã£o em inglÃªs
â”œâ”€â”€ CONTRIBUTING.md                         # Guia de contribuiÃ§Ã£o em chinÃªs
â”œâ”€â”€ CONTRIBUTING-EN.md                      # Guia de contribuiÃ§Ã£o em inglÃªs
â””â”€â”€ LICENSE                                 # LicenÃ§a open source GPL-2.0
```

## ðŸš€ InÃ­cio RÃ¡pido (Docker)

### 1. Iniciar o projeto

Copie o arquivo `.env.example`, renomeie-o para `.env` e configure as variÃ¡veis de ambiente no arquivo `.env` conforme necessÃ¡rio

Execute o seguinte comando para iniciar todos os serviÃ§os em segundo plano:

```bash
docker compose up -d
```

> **Nota: se o download da imagem estiver lento**, no arquivo `docker-compose.yml` original, jÃ¡ fornecemos endereÃ§os de imagem alternativos por meio de **comentÃ¡rios** para sua substituiÃ§Ã£o

### 2. InstruÃ§Ãµes de ConfiguraÃ§Ã£o

#### ConfiguraÃ§Ã£o do Banco de Dados (PostgreSQL)

Configure as informaÃ§Ãµes de conexÃ£o com o banco de dados de acordo com os seguintes parÃ¢metros. MySQL tambÃ©m Ã© suportado e pode ser modificado por conta prÃ³pria:

| Item de ConfiguraÃ§Ã£o | Valor | DescriÃ§Ã£o |
| :--- | :--- | :--- |
| `DB_HOST` | `db` | Nome do serviÃ§o de banco de dados (corresponde ao nome do serviÃ§o no `docker-compose.yml`) |
| `DB_PORT` | `5432` | Porta padrÃ£o do PostgreSQL |
| `DB_USER` | `bettafish` | Nome de usuÃ¡rio do banco de dados |
| `DB_PASSWORD` | `bettafish` | Senha do banco de dados |
| `DB_NAME` | `bettafish` | Nome do banco de dados |
| **Outros** | **Manter padrÃ£o** | Pool de conexÃµes e outros parÃ¢metros do banco de dados devem manter as configuraÃ§Ãµes padrÃ£o. |

#### ConfiguraÃ§Ã£o de Modelos de Linguagem

> Todas as nossas chamadas de LLM utilizam o padrÃ£o de interface API da OpenAI

ApÃ³s concluir a configuraÃ§Ã£o do banco de dados, configure normalmente **todos os parÃ¢metros relacionados ao modelo de linguagem**, garantindo que o sistema possa se conectar ao serviÃ§o de modelo de linguagem escolhido.

ApÃ³s concluir todas as configuraÃ§Ãµes acima e salvar, o sistema estarÃ¡ pronto para funcionar.

## ðŸ”§ Guia de InicializaÃ§Ã£o a Partir do CÃ³digo-Fonte

> Se vocÃª estÃ¡ aprendendo pela primeira vez como construir um sistema de Agents, pode comeÃ§ar com um demo muito simples: [Deep Search Agent Demo](https://github.com/666ghj/DeepSearchAgent-Demo)

### Requisitos do Ambiente

- **Sistema Operacional**: Windows, Linux, MacOS
- **VersÃ£o do Python**: 3.9+
- **Conda**: Anaconda ou Miniconda
- **Banco de Dados**: PostgreSQL (recomendado) ou MySQL
- **MemÃ³ria**: Recomendado 2GB ou mais

### 1. Criar Ambiente

#### Se usar Conda

```bash
# Criar ambiente conda
conda create -n your_conda_name python=3.11
conda activate your_conda_name
```

#### Se usar uv

```bash
# Criar ambiente uv
uv venv --python 3.11 # Criar ambiente 3.11
```

### 2. Instalar DependÃªncias do Sistema para ExportaÃ§Ã£o PDF (Opcional)

HÃ¡ instruÃ§Ãµes detalhadas de configuraÃ§Ã£o nesta parte: [Configurar dependÃªncias necessÃ¡rias](./static/Partial%20README%20for%20PDF%20Exporting/README.md)

### 3. Instalar Pacotes de DependÃªncias

> Se vocÃª pulou a etapa 2, a biblioteca weasyprint pode nÃ£o ser instalada e a funcionalidade de PDF pode nÃ£o funcionar corretamente.

```bash
# InstalaÃ§Ã£o de dependÃªncias bÃ¡sicas
pip install -r requirements.txt

# Comando para versÃ£o uv (instalaÃ§Ã£o mais rÃ¡pida)
uv pip install -r requirements.txt
# Se nÃ£o quiser usar o modelo local de anÃ¡lise de sentimento (necessidade computacional muito baixa, versÃ£o CPU instalada por padrÃ£o), vocÃª pode comentar a seÃ§Ã£o "aprendizado de mÃ¡quina" neste arquivo antes de executar o comando
```

### 4. Instalar Driver de Navegador Playwright

```bash
# Instalar driver de navegador (usado para funcionalidade de crawler)
playwright install chromium
```

### 5. Configurar LLM e Banco de Dados

Copie o arquivo `.env.example` do diretÃ³rio raiz do projeto e renomeie-o para `.env`

Edite o arquivo `.env` e insira suas chaves de API (vocÃª tambÃ©m pode escolher seus prÃ³prios modelos e proxies de busca, veja detalhes no arquivo .env.example do diretÃ³rio raiz ou nas instruÃ§Ãµes em config.py do diretÃ³rio raiz):

```yml
# ====================== ConfiguraÃ§Ã£o do Banco de Dados ======================
# Host do banco de dados, por exemplo localhost ou 127.0.0.1
DB_HOST=your_db_host
# Porta do banco de dados, padrÃ£o 3306
DB_PORT=3306
# Nome de usuÃ¡rio do banco de dados
DB_USER=your_db_user
# Senha do banco de dados
DB_PASSWORD=your_db_password
# Nome do banco de dados
DB_NAME=your_db_name
# Charset do banco de dados, recomendado utf8mb4, compatÃ­vel com emoji
DB_CHARSET=utf8mb4
# Tipo de banco de dados: postgresql ou mysql
DB_DIALECT=postgresql
# O banco de dados nÃ£o precisa de inicializaÃ§Ã£o, serÃ¡ detectado automaticamente ao executar app.py

# ====================== ConfiguraÃ§Ã£o do LLM ======================
# VocÃª pode alterar a API de LLM usada em cada seÃ§Ã£o, qualquer uma compatÃ­vel com o formato de requisiÃ§Ã£o OpenAI funciona
# O arquivo de configuraÃ§Ã£o fornece o LLM recomendado para cada Agent, na primeira implantaÃ§Ã£o consulte as configuraÃ§Ãµes recomendadas

# Insight Agent
INSIGHT_ENGINE_API_KEY=
INSIGHT_ENGINE_BASE_URL=
INSIGHT_ENGINE_MODEL_NAME=

# Media Agent
...
```

### 6. Iniciar o Sistema

#### 6.1 InicializaÃ§Ã£o do Sistema Completo (Recomendado)

```bash
# No diretÃ³rio raiz do projeto, ative o ambiente conda
conda activate your_conda_name

# Inicie a aplicaÃ§Ã£o principal
python app.py
```

Comando de inicializaÃ§Ã£o para versÃ£o uv
```bash
# No diretÃ³rio raiz do projeto, ative o ambiente uv
.venv\Scripts\activate

# Inicie a aplicaÃ§Ã£o principal
python app.py
```

> Nota 1: ApÃ³s o tÃ©rmino de uma execuÃ§Ã£o, o streamlit app pode encerrar de forma anormal e continuar ocupando a porta. Nesse caso, basta encontrar e encerrar o processo que estÃ¡ ocupando a porta

> Nota 2: A coleta de dados requer operaÃ§Ã£o separada, veja as instruÃ§Ãµes em 6.3

Acesse http://localhost:5000 para utilizar o sistema completo

#### 6.2 Iniciar um Agent Individualmente

```bash
# Iniciar QueryEngine
streamlit run SingleEngineApp/query_engine_streamlit_app.py --server.port 8503

# Iniciar MediaEngine
streamlit run SingleEngineApp/media_engine_streamlit_app.py --server.port 8502

# Iniciar InsightEngine
streamlit run SingleEngineApp/insight_engine_streamlit_app.py --server.port 8501
```

#### 6.3 Uso Independente do Sistema de Crawlers

HÃ¡ documentaÃ§Ã£o detalhada de configuraÃ§Ã£o nesta parte: [InstruÃ§Ãµes de uso do MindSpider](./MindSpider/README.md)

<div align="center">
<img src="MindSpider\img\example.png" alt="banner" width="600">

Exemplo de execuÃ§Ã£o do MindSpider
</div>

```bash
# Entrar no diretÃ³rio do crawler
cd MindSpider

# InicializaÃ§Ã£o do projeto
python main.py --setup

# Executar extraÃ§Ã£o de tÃ³picos (obter notÃ­cias em alta e palavras-chave)
python main.py --broad-topic

# Executar fluxo completo do crawler
python main.py --complete --date 2024-01-20

# Executar apenas extraÃ§Ã£o de tÃ³picos
python main.py --broad-topic --date 2024-01-20

# Executar apenas crawling profundo
python main.py --deep-sentiment --platforms xhs dy wb
```

#### 6.4 Ferramenta de GeraÃ§Ã£o de RelatÃ³rio por Linha de Comando

Esta ferramenta pula a fase de execuÃ§Ã£o dos trÃªs motores de anÃ¡lise, lÃª diretamente seus arquivos de log mais recentes e gera o relatÃ³rio consolidado sem necessidade de interface web (tambÃ©m omite a etapa de verificaÃ§Ã£o incremental de arquivos). Por padrÃ£o, gera automaticamente Markdown apÃ³s o PDF (pode ser desativado por parÃ¢metro). Geralmente usada em cenÃ¡rios onde o resultado da geraÃ§Ã£o de relatÃ³rio nÃ£o Ã© satisfatÃ³rio e uma nova tentativa rÃ¡pida Ã© necessÃ¡ria, ou ao depurar o Report Engine.

```bash
# Uso bÃ¡sico (extrai automaticamente o tema do nome do arquivo)
python report_engine_only.py

# Especificar tema do relatÃ³rio
python report_engine_only.py --query "AnÃ¡lise da indÃºstria de engenharia civil"

# Pular geraÃ§Ã£o de PDF (mesmo que o sistema suporte)
python report_engine_only.py --skip-pdf

# Pular geraÃ§Ã£o de Markdown
python report_engine_only.py --skip-markdown

# Exibir logs detalhados
python report_engine_only.py --verbose

# Ver informaÃ§Ãµes de ajuda
python report_engine_only.py --help
```

**DescriÃ§Ã£o das Funcionalidades:**

1. **VerificaÃ§Ã£o automÃ¡tica de dependÃªncias**: O programa verifica automaticamente as dependÃªncias do sistema necessÃ¡rias para geraÃ§Ã£o de PDF e, se estiverem faltando, fornece instruÃ§Ãµes de instalaÃ§Ã£o
2. **ObtenÃ§Ã£o dos arquivos mais recentes**: ObtÃ©m automaticamente os relatÃ³rios de anÃ¡lise mais recentes dos trÃªs diretÃ³rios de motores (`insight_engine_streamlit_reports`, `media_engine_streamlit_reports`, `query_engine_streamlit_reports`)
3. **ConfirmaÃ§Ã£o de arquivos**: Exibe todos os nomes de arquivo selecionados, caminhos e horÃ¡rios de modificaÃ§Ã£o, aguardando confirmaÃ§Ã£o do usuÃ¡rio (digite `y` para continuar por padrÃ£o, `n` para sair)
4. **GeraÃ§Ã£o direta de relatÃ³rio**: Pula o programa de revisÃ£o de incremento de arquivos e chama diretamente o Report Engine para gerar o relatÃ³rio consolidado
5. **Salvamento automÃ¡tico de arquivos**:
   - RelatÃ³rios HTML salvos no diretÃ³rio `final_reports/`
   - RelatÃ³rios PDF (se houver dependÃªncias) salvos no diretÃ³rio `final_reports/pdf/`
   - RelatÃ³rios Markdown (pode ser desativado com `--skip-markdown`) salvos no diretÃ³rio `final_reports/md/`
   - Formato de nomenclatura: `final_report_{tema}_{timestamp}.html/pdf/md`

**ObservaÃ§Ãµes:**

- Certifique-se de que pelo menos um dos trÃªs diretÃ³rios de motores contenha arquivos de relatÃ³rio `.md`
- A ferramenta de linha de comando e a interface web sÃ£o independentes entre si e nÃ£o se afetam mutuamente
- A geraÃ§Ã£o de PDF requer instalaÃ§Ã£o de dependÃªncias do sistema, veja a seÃ§Ã£o "Instalar DependÃªncias do Sistema para ExportaÃ§Ã£o PDF" acima

**Re-renderizaÃ§Ã£o rÃ¡pida dos resultados mais recentes:**

- `regenerate_latest_html.py` / `regenerate_latest_md.py`: Remonta o Document IR a partir dos JSONs de capÃ­tulo da execuÃ§Ã£o mais recente em `CHAPTER_OUTPUT_DIR` e renderiza diretamente HTML ou Markdown.
- `regenerate_latest_pdf.py`: LÃª o IR mais recente de `final_reports/ir` e re-exporta o PDF usando grÃ¡ficos vetoriais SVG.

## âš™ï¸ ConfiguraÃ§Ã£o AvanÃ§ada (Obsoleta, jÃ¡ unificada no arquivo .env do diretÃ³rio raiz do projeto; outros sub-agents herdam automaticamente a configuraÃ§Ã£o do diretÃ³rio raiz)

### Modificar ParÃ¢metros-Chave

#### ParÃ¢metros de ConfiguraÃ§Ã£o dos Agents

Cada Agent possui um arquivo de configuraÃ§Ã£o dedicado que pode ser ajustado conforme a necessidade. Seguem alguns exemplos:

```python
# QueryEngine/utils/config.py
class Config:
    max_reflections = 2           # Rodadas de reflexÃ£o
    max_search_results = 15       # NÃºmero mÃ¡ximo de resultados de busca
    max_content_length = 8000     # Comprimento mÃ¡ximo do conteÃºdo

# MediaEngine/utils/config.py
class Config:
    comprehensive_search_limit = 10  # Limite de busca abrangente
    web_search_limit = 15           # Limite de busca web

# InsightEngine/utils/config.py
class Config:
    default_search_topic_globally_limit = 200    # Limite de busca global
    default_get_comments_limit = 500             # Limite de obtenÃ§Ã£o de comentÃ¡rios
    max_search_results_for_llm = 50              # NÃºmero mÃ¡ximo de resultados passados ao LLM
```

#### ConfiguraÃ§Ã£o do Modelo de AnÃ¡lise de Sentimento

```python
# InsightEngine/tools/sentiment_analyzer.py
SENTIMENT_CONFIG = {
    'model_type': 'multilingual',     # OpÃ§Ãµes: 'bert', 'multilingual', 'qwen', etc.
    'confidence_threshold': 0.8,      # Limiar de confianÃ§a
    'batch_size': 32,                 # Tamanho do lote
    'max_sequence_length': 512,       # Comprimento mÃ¡ximo da sequÃªncia
}
```

### Conectar Diferentes Modelos LLM

Suporta qualquer provedor de LLM no formato de chamada OpenAI. Basta preencher os campos KEY, BASE_URL e MODEL_NAME correspondentes em /config.py.

> O que Ã© o formato de chamada OpenAI? Aqui estÃ¡ um exemplo simples:
>```python
>from openai import OpenAI
>
>client = OpenAI(api_key="your_api_key",
>                base_url="https://aihubmix.com/v1")
>
>response = client.chat.completions.create(
>    model="gpt-4o-mini",
>    messages=[
>        {'role': 'user',
>         'content': "Quais novas oportunidades os modelos de raciocÃ­nio trarÃ£o ao mercado"}
>    ],
>)
>
>complete_response = response.choices[0].message.content
>print(complete_response)
>```

### Alterar o Modelo de AnÃ¡lise de Sentimento

O sistema integra diversos mÃ©todos de anÃ¡lise de sentimento, que podem ser escolhidos conforme a necessidade:

#### 1. AnÃ¡lise de Sentimento MultilÃ­ngue

```bash
cd SentimentAnalysisModel/WeiboMultilingualSentiment
python predict.py --text "This product is amazing!" --lang "en"
```

#### 2. Ajuste Fino do Qwen3 com Poucos ParÃ¢metros

```bash
cd SentimentAnalysisModel/WeiboSentiment_SmallQwen
python predict_universal.py --text "Este evento foi um grande sucesso"
```

#### 3. Modelo Ajustado Fino Baseado em BERT

```bash
# Usar modelo BERT chinÃªs
cd SentimentAnalysisModel/WeiboSentiment_Finetuned/BertChinese-Lora
python predict.py --text "Este produto Ã© realmente muito bom"
```

#### 4. Modelo Ajustado Fino GPT-2 LoRA

```bash
cd SentimentAnalysisModel/WeiboSentiment_Finetuned/GPT2-Lora
python predict.py --text "Hoje nÃ£o estou me sentindo muito bem"
```

#### 5. MÃ©todos Tradicionais de Aprendizado de MÃ¡quina

```bash
cd SentimentAnalysisModel/WeiboSentiment_MachineLearning
python predict.py --model_type "svm" --text "O atendimento precisa melhorar"
```

### Conectar Banco de Dados de NegÃ³cios Personalizado

#### 1. Modificar ConfiguraÃ§Ã£o de ConexÃ£o com o Banco de Dados

```python
# Adicionar configuraÃ§Ã£o do banco de dados de negÃ³cios em config.py
BUSINESS_DB_HOST = "your_business_db_host"
BUSINESS_DB_PORT = 3306
BUSINESS_DB_USER = "your_business_user"
BUSINESS_DB_PASSWORD = "your_business_password"
BUSINESS_DB_NAME = "your_business_database"
```

#### 2. Criar Ferramenta de Acesso a Dados Personalizada

```python
# InsightEngine/tools/custom_db_tool.py
class CustomBusinessDBTool:
    """Ferramenta de consulta a banco de dados de negÃ³cios personalizada"""

    def __init__(self):
        self.connection_config = {
            'host': config.BUSINESS_DB_HOST,
            'port': config.BUSINESS_DB_PORT,
            'user': config.BUSINESS_DB_USER,
            'password': config.BUSINESS_DB_PASSWORD,
            'database': config.BUSINESS_DB_NAME,
        }

    def search_business_data(self, query: str, table: str):
        """Consultar dados de negÃ³cios"""
        # Implemente sua lÃ³gica de negÃ³cios
        pass

    def get_customer_feedback(self, product_id: str):
        """Obter dados de feedback de clientes"""
        # Implemente a lÃ³gica de consulta de feedback de clientes
        pass
```

#### 3. Integrar ao InsightEngine

```python
# Integrar ferramenta personalizada em InsightEngine/agent.py
from .tools.custom_db_tool import CustomBusinessDBTool

class DeepSearchAgent:
    def __init__(self, config=None):
        # ... outro cÃ³digo de inicializaÃ§Ã£o
        self.custom_db_tool = CustomBusinessDBTool()

    def execute_custom_search(self, query: str):
        """Executar busca personalizada de dados de negÃ³cios"""
        return self.custom_db_tool.search_business_data(query, "your_table")
```

### Personalizar Templates de RelatÃ³rio

#### 1. Upload pela Interface Web

O sistema suporta upload de arquivos de template personalizados (formato .md ou .txt), que podem ser selecionados ao gerar relatÃ³rios.

#### 2. Criar Arquivo de Template

Crie novos templates no diretÃ³rio `ReportEngine/report_template/`. Nosso Agent selecionarÃ¡ automaticamente o template mais adequado.

## ðŸ¤ Guia de ContribuiÃ§Ã£o

Aceitamos contribuiÃ§Ãµes de todas as formas!

**Por favor, leia o seguinte guia de contribuiÃ§Ã£o:**
- [CONTRIBUTING.md](./CONTRIBUTING.md)

## ðŸ¦– PrÃ³ximos Passos de Desenvolvimento

Agora o sistema completou a Ãºltima etapa: previsÃ£o! Acesse e confira [MiroFish - Prever Tudo]: https://github.com/666ghj/MiroFish

<div align="center">
<img src="static/image/MiroFish_logo_compressed.jpeg" alt="banner" width="800">
<img src="static/image/banner_compressed.png" alt="banner" width="800">
</div>

## âš ï¸ Aviso Legal

**Aviso Importante: Este projeto destina-se exclusivamente a fins de estudo, pesquisa acadÃªmica e educaÃ§Ã£o**

1. **DeclaraÃ§Ã£o de Conformidade**:
   - Todo o cÃ³digo, ferramentas e funcionalidades deste projeto destinam-se exclusivamente a fins de estudo, pesquisa acadÃªmica e educaÃ§Ã£o
   - Ã‰ estritamente proibido usar este projeto para qualquer finalidade comercial ou atividade lucrativa
   - Ã‰ estritamente proibido usar este projeto para qualquer comportamento ilegal, irregular ou que viole os direitos de terceiros

2. **IsenÃ§Ã£o de Responsabilidade sobre Crawlers**:
   - As funcionalidades de crawler neste projeto destinam-se exclusivamente a fins de aprendizado tÃ©cnico e pesquisa
   - Os usuÃ¡rios devem respeitar o protocolo robots.txt e os termos de uso dos sites-alvo
   - Os usuÃ¡rios devem cumprir as leis e regulamentos aplicÃ¡veis, nÃ£o realizar coleta maliciosa ou uso indevido de dados
   - Quaisquer consequÃªncias legais decorrentes do uso das funcionalidades de crawler sÃ£o de responsabilidade exclusiva do usuÃ¡rio

3. **IsenÃ§Ã£o de Responsabilidade sobre Uso de Dados**:
   - As funcionalidades de anÃ¡lise de dados do projeto destinam-se exclusivamente a pesquisa acadÃªmica
   - Ã‰ estritamente proibido usar os resultados da anÃ¡lise para decisÃµes comerciais ou fins lucrativos
   - Os usuÃ¡rios devem garantir a legalidade e conformidade dos dados analisados

4. **IsenÃ§Ã£o de Responsabilidade TÃ©cnica**:
   - Este projeto Ã© fornecido "como estÃ¡", sem qualquer garantia expressa ou implÃ­cita
   - Os autores nÃ£o se responsabilizam por quaisquer perdas diretas ou indiretas causadas pelo uso deste projeto
   - Os usuÃ¡rios devem avaliar por conta prÃ³pria a adequaÃ§Ã£o e os riscos do projeto

5. **LimitaÃ§Ã£o de Responsabilidade**:
   - Os usuÃ¡rios devem compreender plenamente as leis e regulamentos aplicÃ¡veis antes de usar este projeto
   - Os usuÃ¡rios devem garantir que seu uso esteja em conformidade com as leis e regulamentos locais
   - Quaisquer consequÃªncias decorrentes do uso deste projeto em violaÃ§Ã£o de leis e regulamentos sÃ£o de responsabilidade exclusiva do usuÃ¡rio

**Por favor, leia e compreenda cuidadosamente o aviso legal acima antes de usar este projeto. O uso deste projeto indica que vocÃª concorda e aceita todos os termos acima.**

## ðŸ“„ LicenÃ§a

Este projeto Ã© licenciado sob a [LicenÃ§a GPL-2.0](LICENSE). Para informaÃ§Ãµes detalhadas, consulte o arquivo LICENSE.

## ðŸŽ‰ Suporte e Contato

### Obter Ajuda

Perguntas frequentes: https://github.com/666ghj/BettaFish/issues/185

- **PÃ¡gina do Projeto**: [RepositÃ³rio GitHub](https://github.com/666ghj/BettaFish)
- **Reportar Problemas**: [PÃ¡gina de Issues](https://github.com/666ghj/BettaFish/issues)
- **SugestÃµes de Funcionalidades**: [PÃ¡gina de Discussions](https://github.com/666ghj/BettaFish/discussions)

### InformaÃ§Ãµes de Contato

- **E-mail**: hangjiang@bupt.edu.cn

### CooperaÃ§Ã£o Empresarial

- **Desenvolvimento personalizado para empresas**
- **ServiÃ§os de Big Data**
- **CooperaÃ§Ã£o acadÃªmica**
- **Treinamento tÃ©cnico**

## ðŸ‘¥ Contribuidores

Agradecemos aos seguintes excelentes contribuidores:

[![Contributors](https://contrib.rocks/image?repo=666ghj/BettaFish)](https://github.com/666ghj/BettaFish/graphs/contributors)

## ðŸŒŸ Junte-se ao Grupo Oficial de ComunicaÃ§Ã£o

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=Bem-vindo ao nosso grupo de comunicaÃ§Ã£o tÃ©cnica no QQ!&fontSize=40&fontAlignY=35&desc=Escaneie o QR code abaixo para entrar no grupo&descAlignY=55" alt="Bem-vindo ao nosso grupo de comunicaÃ§Ã£o tÃ©cnica no QQ!" style="width:60%; max-width:900px; display:block; margin:0 auto;">
  <img src="static/image/QQ_Light_Horizenal.png" alt="QR code do grupo de comunicaÃ§Ã£o tÃ©cnica BettaFish" style="width:60%; max-width:360px; display:block; margin:20px auto 0;">
</div>

## ðŸ–¥ï¸ Infraestrutura para Deploy

### OpÃ§Ã£o Recomendada: Docker Compose

```bash
docker compose up -d
```

Sobe dois containers: a **aplicaÃ§Ã£o** + **PostgreSQL 15**.

### Servidor MÃ­nimo

| Recurso | MÃ­nimo | Recomendado |
|---------|--------|-------------|
| RAM | 2 GB | 4 GB+ |
| Disco | 5 GB | 10 GB+ |
| CPU | 2 cores | 4+ cores |
| Python | 3.9+ | 3.11 |
| SO | Linux/macOS/Windows | Linux (Ubuntu) |

### Portas Expostas

| Porta | ServiÃ§o |
|-------|---------|
| 5000 | Flask (app principal) |
| 8501 | InsightEngine (Streamlit) |
| 8502 | MediaEngine (Streamlit) |
| 8503 | QueryEngine (Streamlit) |
| 5444 | PostgreSQL |

### Banco de Dados

- **PostgreSQL 15+** (recomendado) ou MySQL 8.0+
- Inicializado automaticamente no primeiro `python app.py`

### APIs Externas (LLMs + Buscadores)

O sistema usa 6 endpoints de LLM separados, cada um otimizado para sua funÃ§Ã£o:

| ServiÃ§o | FunÃ§Ã£o | Modelo Recomendado | Por que um modelo separado? |
|---------|--------|--------------------|-----------------------------|
| Moonshot Kimi | Insight Engine | kimi-k2 | Contexto longo para analisar grandes volumes de dados |
| Gemini 2.5 Pro | Media + Report Engine | gemini-2.5-pro | Multimodal (entende imagens e vÃ­deos) |
| DeepSeek | Query Engine | deepseek-chat | RÃ¡pido e barato para muitas buscas web |
| Qwen | Forum Host + Keyword Optimizer | qwen-plus | Tarefas leves de moderaÃ§Ã£o e otimizaÃ§Ã£o de queries |

Buscadores web (pelo menos um obrigatÃ³rio):

| ServiÃ§o | Tipo |
|---------|------|
| Tavily | Busca web |
| Anspire | Busca IA |
| Bocha | Busca IA (alternativa) |

> **Posso usar apenas uma LLM?** Sim! Todas as APIs usam formato OpenAI-compatible. VocÃª pode apontar todas as 6 variÃ¡veis no `.env` para o **mesmo modelo** (ex: GPT-4o, Claude ou Gemini), basta repetir a mesma chave/URL/modelo. A separaÃ§Ã£o existe para otimizar **custo e desempenho** â€” modelos baratos onde pode, modelos fortes onde precisa â€” mas funciona perfeitamente com um sÃ³.

### ConfiguraÃ§Ã£o

1. Copiar `.env.example` para `.env`
2. Preencher as **6 chaves de API** dos LLMs (ou a mesma chave repetida)
3. Preencher credenciais do banco de dados
4. Preencher chave de pelo menos um buscador (Tavily, Anspire ou Bocha)

### Deploy Nativo (sem Docker)

```bash
conda create -n bettafish python=3.11
conda activate bettafish
pip install -r requirements.txt
playwright install chromium
python app.py
```

## ðŸ’° Custo por RelatÃ³rio

Cada relatÃ³rio consome ~620K tokens. Comparativo de custo e velocidade:

| Modelo | Custo/relatÃ³rio | Tempo | 100 relatÃ³rios/mÃªs |
|--------|----------------|-------|---------------------|
| Ollama local (qwen2.5:32b) | $0.00 | 3-4 horas | $0 |
| DeepSeek Chat | $0.11 | 8-12 min | ~$11 |
| GPT-4o-mini | $0.17 | 5-8 min | ~$17 |
| Claude Haiku 3.5 | $1.10 | 8-12 min | ~$110 |
| GPT-4o | $2.98 | 10-15 min | ~$298 |
| Claude Sonnet 4 | $4.14 | 10-15 min | ~$414 |

> Todos os modelos usam formato OpenAI-compatible. Basta trocar `API_KEY`, `BASE_URL` e `MODEL_NAME` no `.env`. Pode usar modelos diferentes por engine. Detalhes completos no [RelatÃ³rio do Projeto](./RELATORIO_PROJETO.md#8-custo-de-tokens-e-comparativo-de-llms).

## ðŸ“ˆ EstatÃ­sticas do Projeto

<a href="https://www.star-history.com/#666ghj/BettaFish&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&legend=top-left" />
 </picture>
</a>

![Alt](https://repobeats.axiom.co/api/embed/e04e3eea4674edc39c148a7845c8d09c1b7b1922.svg "Repobeats analytics image")

---

Projeto adaptado da comunidade ARCKHÉ TDS - Marca Arckhe