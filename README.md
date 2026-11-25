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



[English](./README-EN.md) | [PortuguêÂªs](./README.md)

</div>

> [!NOTE]
> ### Fork BR/LATAM ê¢â¬â Adaptado para o mercado brasileiro e latino-americano
>
> | Documento | DescriêÂ§êÂ£o |
> |-----------|-----------|
> | [RelatêÂ³rio Completo do Projeto](./RELATORIO_PROJETO.md) | Tudo sobre o que foi feito, arquitetura, configuraêÂ§êÂ£o, uso e plano de evoluêÂ§êÂ£o |
> | [ConfiguraêÂ§êÂ£o RêÂ¡pida](#%EF%B8%8F-infraestrutura-para-deploy) | Como subir o sistema com Docker + Ollama |
> | [.env.example](./.env.example) | Modelo de configuraêÂ§êÂ£o com todas as variêÂ¡veis documentadas |
>
> **Destaques desta versêÂ£o:**
> - Interface, logs e prompts 100% em portuguêÂªs
> - Busca web global via Tavily (substituindo APIs chinesas)
> - 24 fontes de notêÂ­cias RSS (Brasil, EUA, Europa, AmêÂ©rica do Sul)
> - AnêÂ¡lise de sentimento multilêÂ­ngue com suporte nativo a portuguêÂªs
> - Docker local com Ollama (sem dependêÂªncia de APIs pagas de LLM)

> [!IMPORTANT]
> Confira nosso motor de previsêÂ£o recêÂ©m-lanêÂ§ado: [MiroFish - Motor de inteligêÂªncia coletiva simples e universal para prever tudo](https://github.com/666ghj/MiroFish)
>
> <img src="static/image/MiroFish_logo_compressed.jpeg" alt="banner" width="300">
>
> "Os trêÂªs pilares da anêÂ¡lise de dados" estêÂ£o totalmente integrados: temos a alegria de anunciar o lanêÂ§amento oficial do MiroFish! Com a êÂºltima peêÂ§a do quebra-cabeêÂ§a encaixada, construêÂ­mos o fluxo completo do BettaFish (coleta e anêÂ¡lise de dados) ao MiroFish (previsêÂ£o panorêÂ¢mica). Assim, o ciclo completo dos dados brutos êÂ  tomada de decisêÂ£o inteligente estêÂ¡ concluêÂ­do, tornando possêÂ­vel prever o futuro!

## ê¢Å¡Â¡ VisêÂ£o Geral do Projeto

"**WeiYu**" (Micro-OpiniêÂ£o) êÂ© um sistema inovador de anêÂ¡lise de opiniêÂ£o pêÂºblica baseado em multi-agentes, desenvolvido do zero, que ajuda os usuêÂ¡rios a romper bolhas informacionais, restaurar o panorama real da opiniêÂ£o pêÂºblica, prever tendêÂªncias futuras e auxiliar na tomada de decisêÂµes. O usuêÂ¡rio sêÂ³ precisa expressar sua necessidade de anêÂ¡lise como em uma conversa, e os agentes iniciam automaticamente a anêÂ¡lise de mais de 30 plataformas de mêÂ­dia social nacionais e internacionais e de milhêÂµes de comentêÂ¡rios do pêÂºblico.

> "WeiYu" êÂ© um trocadilho em chinêÂªs que soa como "peixinho". BettaFish êÂ© um peixe de corpo muito pequeno, mas extremamente combativo e bonito, simbolizando "pequeno mas poderoso, sem medo de desafios"

Veja o relatêÂ³rio de pesquisa gerado pelo sistema usando "opiniêÂ£o pêÂºblica da Universidade de Wuhan" como exemplo: [RelatêÂ³rio de AnêÂ¡lise Aprofundada da ReputaêÂ§êÂ£o da Marca da Universidade de Wuhan](./final_reports/final_report__20250827_131630.html)

Veja o vêÂ­deo de uma execuêÂ§êÂ£o completa do sistema usando "opiniêÂ£o pêÂºblica da Universidade de Wuhan" como exemplo: [VêÂ­deo - RelatêÂ³rio de AnêÂ¡lise Aprofundada da ReputaêÂ§êÂ£o da Marca da Universidade de Wuhan](https://www.bilibili.com/video/BV1TH1WBxEWN/?vd_source=da3512187e242ce17dceee4c537ec7a6#reply279744466833)

NêÂ£o apenas na qualidade dos relatêÂ³rios, mas em comparaêÂ§êÂ£o com produtos similares, possuêÂ­mos 6 grandes vantagens:

1. **Monitoramento Global Impulsionado por IA**: Clusters de crawlers de IA operando 24/7, cobrindo integralmente mais de 10 plataformas de mêÂ­dia social nacionais e internacionais como Weibo, Xiaohongshu, Douyin, Kuaishou, etc. AlêÂ©m de capturar conteêÂºdo em alta em tempo real, consegue aprofundar-se em comentêÂ¡rios massivos de usuêÂ¡rios, permitindo ouvir a voz mais autêÂªntica e abrangente do pêÂºblico.

2. **Motor de AnêÂ¡lise Composto que Vai AlêÂ©m dos LLMs**: NêÂ£o dependemos apenas dos 5 tipos de Agents profissionais projetados, mas tambêÂ©m integramos middlewares como modelos ajustados finamente e modelos estatêÂ­sticos. AtravêÂ©s da colaboraêÂ§êÂ£o multi-modelo, garantimos profundidade, precisêÂ£o e perspectivas multidimensionais nos resultados da anêÂ¡lise.

3. **Poderosa Capacidade Multimodal**: Rompendo as limitaêÂ§êÂµes de texto e imagem, consegue analisar em profundidade conteêÂºdo de vêÂ­deos curtos do Douyin, Kuaishou, entre outros, e extrair com precisêÂ£o cartêÂµes de informaêÂ§êÂ£o multimodal estruturada como clima, calendêÂ¡rio e aêÂ§êÂµes de motores de busca modernos, permitindo domêÂ­nio completo das dinêÂ¢micas de opiniêÂ£o pêÂºblica.

4. **Mecanismo de ColaboraêÂ§êÂ£o "FêÂ³rum" entre Agents**: Atribuindo a cada Agent um conjunto êÂºnico de ferramentas e modos de pensamento, introduzimos um modelo de moderador de debates, permitindo colisêÂ£o e debate de cadeias de pensamento atravêÂ©s do mecanismo de "FêÂ³rum". Isso nêÂ£o apenas evita limitaêÂ§êÂµes de pensamento de um êÂºnico modelo e a homogeneizaêÂ§êÂ£o causada pela comunicaêÂ§êÂ£o, mas tambêÂ©m gera inteligêÂªncia coletiva e suporte êÂ  decisêÂ£o de maior qualidade.

5. **IntegraêÂ§êÂ£o Perfeita de Dados PêÂºblicos e Privados**: A plataforma nêÂ£o apenas analisa a opiniêÂ£o pêÂºblica aberta, mas tambêÂ©m fornece interfaces de alta seguranêÂ§a, permitindo integrar perfeitamente bancos de dados internos de negêÂ³cios com dados de opiniêÂ£o pêÂºblica. Quebrando barreiras de dados, oferece poderosa capacidade de anêÂ¡lise de "tendêÂªncias externas + insights internos" para negêÂ³cios verticais.

6. **Framework Leve e Altamente ExtensêÂ­vel**: Baseado em design modular em Python puro, alcanêÂ§a implantaêÂ§êÂ£o leve e com um êÂºnico clique. A estrutura do cêÂ³digo êÂ© clara, e desenvolvedores podem facilmente integrar modelos personalizados e lêÂ³gica de negêÂ³cios, permitindo expansêÂ£o rêÂ¡pida e personalizaêÂ§êÂ£o profunda da plataforma.

**ComeêÂ§a pela opiniêÂ£o pêÂºblica, mas nêÂ£o se limita a ela**. O objetivo do "WeiYu" êÂ© tornar-se um motor de anêÂ¡lise de dados simples e universal que impulsiona qualquer cenêÂ¡rio de negêÂ³cio.

> Por exemplo, vocêÂª sêÂ³ precisa modificar os parêÂ¢metros de API e prompts do conjunto de ferramentas do Agent para transformêÂ¡-lo em um sistema de anêÂ¡lise de mercado no setor financeiro
>
> Segue um têÂ³pico de discussêÂ£o bastante ativo no fêÂ³rum L: https://linux.do/t/topic/1009280
>
> Veja a avaliaêÂ§êÂ£o feita por um membro do fêÂ³rum L [ComparaêÂ§êÂ£o do projeto open source (WeiYu) com manus|minimax|ChatGPT|Perplexity](https://linux.do/t/topic/1148040)

<div align="center">
<img src="static/image/system_schematic.png" alt="banner" width="800">

Diga adeus aos painêÂ©is de dados tradicionais. No "WeiYu", tudo comeêÂ§a com uma simples pergunta - vocêÂª sêÂ³ precisa expressar sua necessidade de anêÂ¡lise como em uma conversa
</div>

## ê°Å¸Âªâ Patrocinadores

PatrocêÂ­nio de API de modelos LLM: <a href="https://aihubmix.com/?aff=8Ds9" target="_blank"><img src="./static/image/logo_aihubmix.png" alt="666ghj%2FBettaFish | Trendshift" height="40"/></a>

<details>
<summary>Provedor de capacidades centrais de agentes inteligentes como busca conectada por IA, anêÂ¡lise de arquivos e captura de conteêÂºdo web:</a><span style="margin-left: 10px"><a href="https://open.anspire.cn/?share_code=3E1FUOUH" target="_blank"><img src="./static/image/logo_anspire.png" alt="666ghj%2FBettaFish | Trendshift" height="50"/></a></summary>
A Plataforma Aberta Anspire (Anspire Open) êÂ© um provedor lêÂ­der de infraestrutura para a era dos agentes inteligentes. Oferecemos aos desenvolvedores a pilha de capacidades centrais necessêÂ¡rias para construir agentes poderosos, com serviêÂ§os jêÂ¡ disponêÂ­veis como busca conectada por IA [mêÂºltiplas versêÂµes, preêÂ§os extremamente competitivos], anêÂ¡lise de arquivos [gratuita por tempo limitado] e captura de conteêÂºdo web [gratuita por tempo limitado], automaêÂ§êÂ£o de navegador em nuvem (Anspire Browser Agent) [em beta], reescrita em mêÂºltiplas rodadas e mais, fornecendo continuamente uma base sêÂ³lida para que agentes inteligentes se conectem e operem no complexo mundo digital. IntegraêÂ§êÂ£o perfeita com plataformas de agentes populares como Dify, Coze, Yuanqi, entre outras. AtravêÂ©s de um sistema de cobranêÂ§a transparente por pontos e design modular, oferecemos suporte personalizado eficiente e de baixo custo para empresas, acelerando o processo de modernizaêÂ§êÂ£o inteligente.
</details>

## ê°Å¸Ââê¯Â¸Â Arquitetura do Sistema

### Diagrama da Arquitetura Geral

**Insight Agent** MineraêÂ§êÂ£o de banco de dados privado: Agente de IA para anêÂ¡lise aprofundada de bancos de dados privados de opiniêÂ£o pêÂºblica

**Media Agent** AnêÂ¡lise de conteêÂºdo multimodal: Agente de IA com poderosas capacidades multimodais

**Query Agent** Busca precisa de informaêÂ§êÂµes: Agente de IA com capacidade de busca web nacional e internacional

**Report Agent** GeraêÂ§êÂ£o inteligente de relatêÂ³rios: Agente de IA para geraêÂ§êÂ£o de relatêÂ³rios em mêÂºltiplas rodadas com templates integrados

<div align="center">
<img src="static/image/framework.png" alt="banner" width="800">
</div>

### Fluxo Completo de Uma AnêÂ¡lise

| Etapa | Nome da Fase | OperaêÂ§êÂ£o Principal | Componentes Envolvidos | CaracterêÂ­sticas de Loop |
|------|----------|----------|----------|----------|
| 1 | Pergunta do UsuêÂ¡rio | AplicaêÂ§êÂ£o principal Flask recebe a consulta | AplicaêÂ§êÂ£o principal Flask | - |
| 2 | InicializaêÂ§êÂ£o Paralela | TrêÂªs Agents comeêÂ§am a trabalhar simultaneamente | Query Agent, Media Agent, Insight Agent | - |
| 3 | AnêÂ¡lise Preliminar | Cada Agent usa suas ferramentas exclusivas para busca geral | Cada Agent + conjunto de ferramentas exclusivo | - |
| 4 | FormulaêÂ§êÂ£o de EstratêÂ©gia | FormulaêÂ§êÂ£o de estratêÂ©gia de pesquisa segmentada com base nos resultados preliminares | MêÂ³dulo de decisêÂ£o interno de cada Agent | - |
| 5-N | **Fase de Loop** | **ColaboraêÂ§êÂ£o no FêÂ³rum + Pesquisa Aprofundada** | **ForumEngine + Todos os Agents** | **Loop em mêÂºltiplas rodadas** |
| 5.1 | Pesquisa Aprofundada | Cada Agent realiza busca especializada guiado pelo moderador do fêÂ³rum | Cada Agent + mecanismo de reflexêÂ£o + orientaêÂ§êÂ£o do fêÂ³rum | Cada rodada do loop |
| 5.2 | ColaboraêÂ§êÂ£o no FêÂ³rum | ForumEngine monitora falas dos Agents e gera orientaêÂ§êÂ£o do moderador | ForumEngine + LLM moderador | Cada rodada do loop |
| 5.3 | Troca e FusêÂ£o | Cada Agent ajusta sua direêÂ§êÂ£o de pesquisa com base na discussêÂ£o | Cada Agent + ferramenta forum_reader | Cada rodada do loop |
| N+1 | IntegraêÂ§êÂ£o de Resultados | Report Agent coleta todos os resultados de anêÂ¡lise e conteêÂºdo do fêÂ³rum | Report Agent | - |
| N+2 | RepresentaêÂ§êÂ£o IntermediêÂ¡ria IR | SeleêÂ§êÂ£o dinêÂ¢mica de template e estilo, geraêÂ§êÂ£o de metadados em mêÂºltiplas rodadas, montagem em representaêÂ§êÂ£o intermediêÂ¡ria IR | Report Agent + motor de templates | - |
| N+3 | GeraêÂ§êÂ£o do RelatêÂ³rio | VerificaêÂ§êÂ£o de qualidade por blocos, renderizaêÂ§êÂ£o em relatêÂ³rio HTML interativo baseado em IR | Report Agent + motor de montagem | - |

### Estrutura de CêÂ³digo do Projeto

```
BettaFish/
ê¢âÅê¢ââ¬ê¢ââ¬ QueryEngine/                            # Agent de busca ampla de notêÂ­cias nacionais e internacionais
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ agent.py                            # LêÂ³gica principal do Agent, coordena fluxo de busca e anêÂ¡lise
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ llms/                               # Encapsulamento de interface LLM
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ nodes/                              # NêÂ³s de processamento: busca, formataêÂ§êÂ£o, resumo, etc.
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ tools/                              # Conjunto de ferramentas de busca de notêÂ­cias nacionais e internacionais
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ utils/                              # FunêÂ§êÂµes utilitêÂ¡rias
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ state/                              # Gerenciamento de estado
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ prompts/                            # Templates de prompts
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢âÅê¢ââ¬ê¢ââ¬ MediaEngine/                            # Agent de compreensêÂ£o multimodal poderoso
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ agent.py                            # LêÂ³gica principal do Agent, processa conteêÂºdo multimodal como vêÂ­deo/imagem
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ llms/                               # Encapsulamento de interface LLM
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ nodes/                              # NêÂ³s de processamento: busca, formataêÂ§êÂ£o, resumo, etc.
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ tools/                              # Conjunto de ferramentas de busca multimodal
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ utils/                              # FunêÂ§êÂµes utilitêÂ¡rias
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ state/                              # Gerenciamento de estado
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ prompts/                            # Templates de prompts
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢âÅê¢ââ¬ê¢ââ¬ InsightEngine/                          # Agent de mineraêÂ§êÂ£o de banco de dados privado
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ agent.py                            # LêÂ³gica principal do Agent, coordena consulta e anêÂ¡lise do banco de dados
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ llms/                               # Encapsulamento de interface LLM
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ base.py                         # Cliente unificado compatêÂ­vel com OpenAI
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ nodes/                              # NêÂ³s de processamento: busca, formataêÂ§êÂ£o, resumo, etc.
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ base_node.py                    # Classe base de nêÂ³
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ search_node.py                  # NêÂ³ de busca
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ formatting_node.py              # NêÂ³ de formataêÂ§êÂ£o
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ report_structure_node.py        # NêÂ³ de estrutura de relatêÂ³rio
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ summary_node.py                 # NêÂ³ de resumo
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ tools/                              # Conjunto de ferramentas de consulta e anêÂ¡lise de banco de dados
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ keyword_optimizer.py            # Middleware de otimizaêÂ§êÂ£o de palavras-chave Qwen
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ search.py                       # Conjunto de ferramentas de operaêÂ§êÂ£o de banco de dados (busca de têÂ³picos, obtenêÂ§êÂ£o de comentêÂ¡rios, etc.)
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ sentiment_analyzer.py           # Ferramenta integrada de anêÂ¡lise de sentimento
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ utils/                              # FunêÂ§êÂµes utilitêÂ¡rias
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ config.py                       # Gerenciamento de configuraêÂ§êÂ£o
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ db.py                           # Motor assêÂ­ncrono SQLAlchemy e encapsulamento de consulta somente leitura
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ text_processing.py              # Ferramentas de processamento de texto
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ state/                              # Gerenciamento de estado
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ state.py                        # DefiniêÂ§êÂ£o de estado do Agent
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ prompts/                            # Templates de prompts
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ prompts.py                      # Diversos prompts
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ __init__.py
ê¢âÅê¢ââ¬ê¢ââ¬ ReportEngine/                           # Agent de geraêÂ§êÂ£o de relatêÂ³rios em mêÂºltiplas rodadas
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ agent.py                            # Orquestrador geral: seleêÂ§êÂ£o de templateê¢â âlayoutê¢â âextensêÂ£oê¢â âcapêÂ­tulosê¢â ârenderizaêÂ§êÂ£o
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ flask_interface.py                  # Entrada Flask/SSE, gerencia fila de tarefas e eventos de streaming
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ llms/                               # Encapsulamento de LLM compatêÂ­vel com OpenAI
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ base.py                         # Cliente unificado com streaming/retry
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ core/                               # Funcionalidades centrais: parsing de template, armazenamento de capêÂ­tulos, montagem de documento
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ template_parser.py              # Fatiamento de template Markdown e geraêÂ§êÂ£o de slug
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ chapter_storage.py              # DiretêÂ³rio run de capêÂ­tulos, manifest e escrita de fluxo raw
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ stitcher.py                     # Montador de Document IR, preenchimento de êÂ¢ncoras/metadados
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ ir/                                 # Contrato e validaêÂ§êÂ£o de RepresentaêÂ§êÂ£o IntermediêÂ¡ria (IR) do relatêÂ³rio
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ schema.py                       # DefiniêÂ§êÂ£o de constantes de Schema de blocos/marcadores
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ validator.py                    # Validador de estrutura JSON de capêÂ­tulos
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ nodes/                              # NêÂ³s de inferêÂªncia do fluxo completo
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ base_node.py                    # Classe base de nêÂ³ + hooks de log/estado
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ template_selection_node.py      # Coleta de candidatos de template e seleêÂ§êÂ£o por LLM
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ document_layout_node.py         # Design de têÂ­tulo/êÂ­ndice/tema
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ word_budget_node.py             # Planejamento de extensêÂ£o e geraêÂ§êÂ£o de instruêÂ§êÂµes por capêÂ­tulo
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ chapter_generation_node.py      # GeraêÂ§êÂ£o JSON por capêÂ­tulo + validaêÂ§êÂ£o
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ prompts/                            # Biblioteca de prompts e descriêÂ§êÂµes de Schema
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ prompts.py                      # Prompts de seleêÂ§êÂ£o de template/layout/extensêÂ£o/capêÂ­tulo
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ renderers/                          # Renderizadores de IR
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ html_renderer.py               # Document IRê¢â âHTML interativo
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ pdf_renderer.py                # HTMLê¢â âexportaêÂ§êÂ£o PDF (WeasyPrint)
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ pdf_layout_optimizer.py         # Otimizador de layout PDF
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ chart_to_svg.py                # Ferramenta de conversêÂ£o de grêÂ¡ficos para SVG
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ state/                              # Modelos de estado de tarefa/metadados
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ state.py                        # ReportState e ferramentas de serializaêÂ§êÂ£o
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ utils/                              # ConfiguraêÂ§êÂ£o e ferramentas auxiliares
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ config.py                       # Pydantic Settings e auxiliar de impressêÂ£o
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ dependency_check.py             # Ferramenta de verificaêÂ§êÂ£o de dependêÂªncias
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ json_parser.py                  # Ferramenta de parsing JSON
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ chart_validator.py              # Ferramenta de validaêÂ§êÂ£o de grêÂ¡ficos
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ chart_repair_api.py             # API de reparo de grêÂ¡ficos
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ report_template/                    # Biblioteca de templates Markdown
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ äÂ¼ÂäÂ¸Å¡ê¥âÂê§â°Åê¥Â£Â°ê¨Âªâ°ê¥Ëâ ê¦Å¾Âê¦Å Â¥ê¥âÅ .md
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ __init__.py
ê¢âÅê¢ââ¬ê¢ââ¬ ForumEngine/                            # Motor de fêÂ³rum: mecanismo de colaboraêÂ§êÂ£o entre Agents
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ monitor.py                          # NêÂºcleo de monitoramento de logs e gerenciamento do fêÂ³rum
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ llm_host.py                         # MêÂ³dulo LLM do moderador do fêÂ³rum
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ __init__.py
ê¢âÅê¢ââ¬ê¢ââ¬ MindSpider/                             # Sistema de crawlers de mêÂ­dias sociais
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ main.py                             # Ponto de entrada principal do crawler
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ config.py                           # Arquivo de configuraêÂ§êÂ£o do crawler
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ BroadTopicExtraction/               # MêÂ³dulo de extraêÂ§êÂ£o de têÂ³picos
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ main.py                         # Programa principal de extraêÂ§êÂ£o de têÂ³picos
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ database_manager.py             # Gerenciador de banco de dados
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ get_today_news.py               # ObtenêÂ§êÂ£o de notêÂ­cias do dia
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ topic_extractor.py              # Extrator de têÂ³picos
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ DeepSentimentCrawling/              # MêÂ³dulo de crawling profundo de opiniêÂ£o pêÂºblica
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ main.py                         # Programa principal de crawling profundo
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ keyword_manager.py              # Gerenciador de palavras-chave
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ platform_crawler.py             # Gerenciador de crawlers por plataforma
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ MediaCrawler/                   # NêÂºcleo de crawlers de mêÂ­dias sociais
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ main.py
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ config/                     # ConfiguraêÂ§êÂµes por plataforma
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ media_platform/             # ImplementaêÂ§êÂ£o de crawlers por plataforma
ê¢ââ   ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ schema/                             # DefiniêÂ§êÂ£o de estrutura do banco de dados
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ db_manager.py                   # Gerenciador de banco de dados
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ init_database.py                # Script de inicializaêÂ§êÂ£o do banco de dados
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ mindspider_tables.sql           # SQL da estrutura de tabelas do banco de dados
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ models_bigdata.py               # Mapeamento SQLAlchemy das tabelas de opiniêÂ£o pêÂºblica em larga escala
ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ models_sa.py                    # Modelos ORM de tabelas estendidas DailyTopic/Task
ê¢âÅê¢ââ¬ê¢ââ¬ SentimentAnalysisModel/                 # ColeêÂ§êÂ£o de modelos de anêÂ¡lise de sentimento
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ WeiboSentiment_Finetuned/           # Modelos BERT/GPT-2 ajustados finamente
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ BertChinese-Lora/               # Ajuste fino LoRA do BERT chinêÂªs
ê¢ââ   ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ train.py
ê¢ââ   ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ predict.py
ê¢ââ   ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ GPT2-Lora/                      # Ajuste fino LoRA do GPT-2
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ train.py
ê¢ââ   ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ predict.py
ê¢ââ   ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ WeiboMultilingualSentiment/         # AnêÂ¡lise de sentimento multilêÂ­ngue
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ train.py
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ predict.py
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ WeiboSentiment_SmallQwen/           # Ajuste fino do Qwen3 com poucos parêÂ¢metros
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ train.py
ê¢ââ   ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ predict_universal.py
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ WeiboSentiment_MachineLearning/     # MêÂ©todos tradicionais de aprendizado de mêÂ¡quina
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ train.py
ê¢ââ       ê¢âÅê¢ââ¬ê¢ââ¬ predict.py
ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢âÅê¢ââ¬ê¢ââ¬ SingleEngineApp/                        # AplicaêÂ§êÂµes Streamlit de Agents individuais
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ query_engine_streamlit_app.py       # AplicaêÂ§êÂ£o independente do QueryEngine
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ media_engine_streamlit_app.py       # AplicaêÂ§êÂ£o independente do MediaEngine
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ insight_engine_streamlit_app.py     # AplicaêÂ§êÂ£o independente do InsightEngine
ê¢âÅê¢ââ¬ê¢ââ¬ query_engine_streamlit_reports/         # SaêÂ­da da aplicaêÂ§êÂ£o individual do QueryEngine
ê¢âÅê¢ââ¬ê¢ââ¬ media_engine_streamlit_reports/         # SaêÂ­da da aplicaêÂ§êÂ£o individual do MediaEngine
ê¢âÅê¢ââ¬ê¢ââ¬ insight_engine_streamlit_reports/       # SaêÂ­da da aplicaêÂ§êÂ£o individual do InsightEngine
ê¢âÅê¢ââ¬ê¢ââ¬ templates/                              # Templates do frontend Flask
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ index.html                          # HTML da interface principal
ê¢âÅê¢ââ¬ê¢ââ¬ static/                                 # Recursos estêÂ¡ticos
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ image/                              # Recursos de imagem
ê¢ââ   ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ Partial README for PDF Exporting/   # InstruêÂ§êÂµes de configuraêÂ§êÂ£o de dependêÂªncias para exportaêÂ§êÂ£o PDF
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ v2_report_example/                  # Exemplos de renderizaêÂ§êÂ£o de relatêÂ³rios
ê¢ââ       ê¢ââê¢ââ¬ê¢ââ¬ report_all_blocks_demo/         # DemonstraêÂ§êÂ£o de todos os tipos de blocos (HTML/PDF/MD)
ê¢âÅê¢ââ¬ê¢ââ¬ logs/                                   # DiretêÂ³rio de logs de execuêÂ§êÂ£o
ê¢âÅê¢ââ¬ê¢ââ¬ final_reports/                          # Arquivos de relatêÂ³rios finais gerados
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ ir/                                 # Arquivos JSON de IR do relatêÂ³rio
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ *.html                              # RelatêÂ³rios HTML finais
ê¢âÅê¢ââ¬ê¢ââ¬ utils/                                  # FunêÂ§êÂµes utilitêÂ¡rias gerais
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ forum_reader.py                     # Ferramenta de comunicaêÂ§êÂ£o do fêÂ³rum entre Agents
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ github_issues.py                    # GeraêÂ§êÂ£o unificada de links para GitHub Issues e mensagens de erro
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ retry_helper.py                     # Ferramenta de mecanismo de retry para requisiêÂ§êÂµes de rede
ê¢âÅê¢ââ¬ê¢ââ¬ tests/                                  # Testes unitêÂ¡rios e de integraêÂ§êÂ£o
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ run_tests.py                        # Script de entrada do pytest
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ test_monitor.py                     # Testes unitêÂ¡rios do monitoramento do ForumEngine
ê¢ââ   ê¢âÅê¢ââ¬ê¢ââ¬ test_report_engine_sanitization.py  # Testes de seguranêÂ§a do ReportEngine
ê¢ââ   ê¢ââê¢ââ¬ê¢ââ¬ ...
ê¢âÅê¢ââ¬ê¢ââ¬ app.py                                  # Ponto de entrada da aplicaêÂ§êÂ£o Flask principal
ê¢âÅê¢ââ¬ê¢ââ¬ config.py                               # Arquivo de configuraêÂ§êÂ£o global
ê¢âÅê¢ââ¬ê¢ââ¬ .env.example                            # Arquivo de exemplo de variêÂ¡veis de ambiente
ê¢âÅê¢ââ¬ê¢ââ¬ docker-compose.yml                      # ConfiguraêÂ§êÂ£o de orquestraêÂ§êÂ£o multi-serviêÂ§o Docker
ê¢âÅê¢ââ¬ê¢ââ¬ Dockerfile                              # Arquivo de construêÂ§êÂ£o de imagem Docker
ê¢âÅê¢ââ¬ê¢ââ¬ requirements.txt                        # Lista de dependêÂªncias Python
ê¢âÅê¢ââ¬ê¢ââ¬ regenerate_latest_html.py               # Remontagem e renderizaêÂ§êÂ£o HTML usando os capêÂ­tulos mais recentes
ê¢âÅê¢ââ¬ê¢ââ¬ regenerate_latest_md.py                 # Remontagem e renderizaêÂ§êÂ£o Markdown usando os capêÂ­tulos mais recentes
ê¢âÅê¢ââ¬ê¢ââ¬ regenerate_latest_pdf.py                # Script de regeneraêÂ§êÂ£o de PDF
ê¢âÅê¢ââ¬ê¢ââ¬ report_engine_only.py                   # VersêÂ£o de linha de comando do Report Engine
ê¢âÅê¢ââ¬ê¢ââ¬ README.md                               # DocumentaêÂ§êÂ£o em portuguêÂªs
ê¢âÅê¢ââ¬ê¢ââ¬ README-EN.md                            # DocumentaêÂ§êÂ£o em inglêÂªs
ê¢âÅê¢ââ¬ê¢ââ¬ CONTRIBUTING.md                         # Guia de contribuiêÂ§êÂ£o em chinêÂªs
ê¢âÅê¢ââ¬ê¢ââ¬ CONTRIBUTING-EN.md                      # Guia de contribuiêÂ§êÂ£o em inglêÂªs
ê¢ââê¢ââ¬ê¢ââ¬ LICENSE                                 # LicenêÂ§a open source GPL-2.0
```

## ê°Å¸Å¡â¬ InêÂ­cio RêÂ¡pido (Docker)

### 1. Iniciar o projeto

Copie o arquivo `.env.example`, renomeie-o para `.env` e configure as variêÂ¡veis de ambiente no arquivo `.env` conforme necessêÂ¡rio

Execute o seguinte comando para iniciar todos os serviêÂ§os em segundo plano:

```bash
docker compose up -d
```

> **Nota: se o download da imagem estiver lento**, no arquivo `docker-compose.yml` original, jêÂ¡ fornecemos endereêÂ§os de imagem alternativos por meio de **comentêÂ¡rios** para sua substituiêÂ§êÂ£o

### 2. InstruêÂ§êÂµes de ConfiguraêÂ§êÂ£o

#### ConfiguraêÂ§êÂ£o do Banco de Dados (PostgreSQL)

Configure as informaêÂ§êÂµes de conexêÂ£o com o banco de dados de acordo com os seguintes parêÂ¢metros. MySQL tambêÂ©m êÂ© suportado e pode ser modificado por conta prêÂ³pria:

| Item de ConfiguraêÂ§êÂ£o | Valor | DescriêÂ§êÂ£o |
| :--- | :--- | :--- |
| `DB_HOST` | `db` | Nome do serviêÂ§o de banco de dados (corresponde ao nome do serviêÂ§o no `docker-compose.yml`) |
| `DB_PORT` | `5432` | Porta padrêÂ£o do PostgreSQL |
| `DB_USER` | `bettafish` | Nome de usuêÂ¡rio do banco de dados |
| `DB_PASSWORD` | `bettafish` | Senha do banco de dados |
| `DB_NAME` | `bettafish` | Nome do banco de dados |
| **Outros** | **Manter padrêÂ£o** | Pool de conexêÂµes e outros parêÂ¢metros do banco de dados devem manter as configuraêÂ§êÂµes padrêÂ£o. |

#### ConfiguraêÂ§êÂ£o de Modelos de Linguagem

> Todas as nossas chamadas de LLM utilizam o padrêÂ£o de interface API da OpenAI

ApêÂ³s concluir a configuraêÂ§êÂ£o do banco de dados, configure normalmente **todos os parêÂ¢metros relacionados ao modelo de linguagem**, garantindo que o sistema possa se conectar ao serviêÂ§o de modelo de linguagem escolhido.

ApêÂ³s concluir todas as configuraêÂ§êÂµes acima e salvar, o sistema estarêÂ¡ pronto para funcionar.

## ê°Å¸âÂ§ Guia de InicializaêÂ§êÂ£o a Partir do CêÂ³digo-Fonte

> Se vocêÂª estêÂ¡ aprendendo pela primeira vez como construir um sistema de Agents, pode comeêÂ§ar com um demo muito simples: [Deep Search Agent Demo](https://github.com/666ghj/DeepSearchAgent-Demo)

### Requisitos do Ambiente

- **Sistema Operacional**: Windows, Linux, MacOS
- **VersêÂ£o do Python**: 3.9+
- **Conda**: Anaconda ou Miniconda
- **Banco de Dados**: PostgreSQL (recomendado) ou MySQL
- **MemêÂ³ria**: Recomendado 2GB ou mais

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

### 2. Instalar DependêÂªncias do Sistema para ExportaêÂ§êÂ£o PDF (Opcional)

HêÂ¡ instruêÂ§êÂµes detalhadas de configuraêÂ§êÂ£o nesta parte: [Configurar dependêÂªncias necessêÂ¡rias](./static/Partial%20README%20for%20PDF%20Exporting/README.md)

### 3. Instalar Pacotes de DependêÂªncias

> Se vocêÂª pulou a etapa 2, a biblioteca weasyprint pode nêÂ£o ser instalada e a funcionalidade de PDF pode nêÂ£o funcionar corretamente.

```bash
# InstalaêÂ§êÂ£o de dependêÂªncias bêÂ¡sicas
pip install -r requirements.txt

# Comando para versêÂ£o uv (instalaêÂ§êÂ£o mais rêÂ¡pida)
uv pip install -r requirements.txt
# Se nêÂ£o quiser usar o modelo local de anêÂ¡lise de sentimento (necessidade computacional muito baixa, versêÂ£o CPU instalada por padrêÂ£o), vocêÂª pode comentar a seêÂ§êÂ£o "aprendizado de mêÂ¡quina" neste arquivo antes de executar o comando
```

### 4. Instalar Driver de Navegador Playwright

```bash
# Instalar driver de navegador (usado para funcionalidade de crawler)
playwright install chromium
```

### 5. Configurar LLM e Banco de Dados

Copie o arquivo `.env.example` do diretêÂ³rio raiz do projeto e renomeie-o para `.env`

Edite o arquivo `.env` e insira suas chaves de API (vocêÂª tambêÂ©m pode escolher seus prêÂ³prios modelos e proxies de busca, veja detalhes no arquivo .env.example do diretêÂ³rio raiz ou nas instruêÂ§êÂµes em config.py do diretêÂ³rio raiz):

```yml
# ====================== ConfiguraêÂ§êÂ£o do Banco de Dados ======================
# Host do banco de dados, por exemplo localhost ou 127.0.0.1
DB_HOST=your_db_host
# Porta do banco de dados, padrêÂ£o 3306
DB_PORT=3306
# Nome de usuêÂ¡rio do banco de dados
DB_USER=your_db_user
# Senha do banco de dados
DB_PASSWORD=your_db_password
# Nome do banco de dados
DB_NAME=your_db_name
# Charset do banco de dados, recomendado utf8mb4, compatêÂ­vel com emoji
DB_CHARSET=utf8mb4
# Tipo de banco de dados: postgresql ou mysql
DB_DIALECT=postgresql
# O banco de dados nêÂ£o precisa de inicializaêÂ§êÂ£o, serêÂ¡ detectado automaticamente ao executar app.py

# ====================== ConfiguraêÂ§êÂ£o do LLM ======================
# VocêÂª pode alterar a API de LLM usada em cada seêÂ§êÂ£o, qualquer uma compatêÂ­vel com o formato de requisiêÂ§êÂ£o OpenAI funciona
# O arquivo de configuraêÂ§êÂ£o fornece o LLM recomendado para cada Agent, na primeira implantaêÂ§êÂ£o consulte as configuraêÂ§êÂµes recomendadas

# Insight Agent
INSIGHT_ENGINE_API_KEY=
INSIGHT_ENGINE_BASE_URL=
INSIGHT_ENGINE_MODEL_NAME=

# Media Agent
...
```

### 6. Iniciar o Sistema

#### 6.1 InicializaêÂ§êÂ£o do Sistema Completo (Recomendado)

```bash
# No diretêÂ³rio raiz do projeto, ative o ambiente conda
conda activate your_conda_name

# Inicie a aplicaêÂ§êÂ£o principal
python app.py
```

Comando de inicializaêÂ§êÂ£o para versêÂ£o uv
```bash
# No diretêÂ³rio raiz do projeto, ative o ambiente uv
.venv\Scripts\activate

# Inicie a aplicaêÂ§êÂ£o principal
python app.py
```

> Nota 1: ApêÂ³s o têÂ©rmino de uma execuêÂ§êÂ£o, o streamlit app pode encerrar de forma anormal e continuar ocupando a porta. Nesse caso, basta encontrar e encerrar o processo que estêÂ¡ ocupando a porta

> Nota 2: A coleta de dados requer operaêÂ§êÂ£o separada, veja as instruêÂ§êÂµes em 6.3

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

HêÂ¡ documentaêÂ§êÂ£o detalhada de configuraêÂ§êÂ£o nesta parte: [InstruêÂ§êÂµes de uso do MindSpider](./MindSpider/README.md)

<div align="center">
<img src="MindSpider\img\example.png" alt="banner" width="600">

Exemplo de execuêÂ§êÂ£o do MindSpider
</div>

```bash
# Entrar no diretêÂ³rio do crawler
cd MindSpider

# InicializaêÂ§êÂ£o do projeto
python main.py --setup

# Executar extraêÂ§êÂ£o de têÂ³picos (obter notêÂ­cias em alta e palavras-chave)
python main.py --broad-topic

# Executar fluxo completo do crawler
python main.py --complete --date 2024-01-20

# Executar apenas extraêÂ§êÂ£o de têÂ³picos
python main.py --broad-topic --date 2024-01-20

# Executar apenas crawling profundo
python main.py --deep-sentiment --platforms xhs dy wb
```

#### 6.4 Ferramenta de GeraêÂ§êÂ£o de RelatêÂ³rio por Linha de Comando

Esta ferramenta pula a fase de execuêÂ§êÂ£o dos trêÂªs motores de anêÂ¡lise, lêÂª diretamente seus arquivos de log mais recentes e gera o relatêÂ³rio consolidado sem necessidade de interface web (tambêÂ©m omite a etapa de verificaêÂ§êÂ£o incremental de arquivos). Por padrêÂ£o, gera automaticamente Markdown apêÂ³s o PDF (pode ser desativado por parêÂ¢metro). Geralmente usada em cenêÂ¡rios onde o resultado da geraêÂ§êÂ£o de relatêÂ³rio nêÂ£o êÂ© satisfatêÂ³rio e uma nova tentativa rêÂ¡pida êÂ© necessêÂ¡ria, ou ao depurar o Report Engine.

```bash
# Uso bêÂ¡sico (extrai automaticamente o tema do nome do arquivo)
python report_engine_only.py

# Especificar tema do relatêÂ³rio
python report_engine_only.py --query "AnêÂ¡lise da indêÂºstria de engenharia civil"

# Pular geraêÂ§êÂ£o de PDF (mesmo que o sistema suporte)
python report_engine_only.py --skip-pdf

# Pular geraêÂ§êÂ£o de Markdown
python report_engine_only.py --skip-markdown

# Exibir logs detalhados
python report_engine_only.py --verbose

# Ver informaêÂ§êÂµes de ajuda
python report_engine_only.py --help
```

**DescriêÂ§êÂ£o das Funcionalidades:**

1. **VerificaêÂ§êÂ£o automêÂ¡tica de dependêÂªncias**: O programa verifica automaticamente as dependêÂªncias do sistema necessêÂ¡rias para geraêÂ§êÂ£o de PDF e, se estiverem faltando, fornece instruêÂ§êÂµes de instalaêÂ§êÂ£o
2. **ObtenêÂ§êÂ£o dos arquivos mais recentes**: ObtêÂ©m automaticamente os relatêÂ³rios de anêÂ¡lise mais recentes dos trêÂªs diretêÂ³rios de motores (`insight_engine_streamlit_reports`, `media_engine_streamlit_reports`, `query_engine_streamlit_reports`)
3. **ConfirmaêÂ§êÂ£o de arquivos**: Exibe todos os nomes de arquivo selecionados, caminhos e horêÂ¡rios de modificaêÂ§êÂ£o, aguardando confirmaêÂ§êÂ£o do usuêÂ¡rio (digite `y` para continuar por padrêÂ£o, `n` para sair)
4. **GeraêÂ§êÂ£o direta de relatêÂ³rio**: Pula o programa de revisêÂ£o de incremento de arquivos e chama diretamente o Report Engine para gerar o relatêÂ³rio consolidado
5. **Salvamento automêÂ¡tico de arquivos**:
   - RelatêÂ³rios HTML salvos no diretêÂ³rio `final_reports/`
   - RelatêÂ³rios PDF (se houver dependêÂªncias) salvos no diretêÂ³rio `final_reports/pdf/`
   - RelatêÂ³rios Markdown (pode ser desativado com `--skip-markdown`) salvos no diretêÂ³rio `final_reports/md/`
   - Formato de nomenclatura: `final_report_{tema}_{timestamp}.html/pdf/md`

**ObservaêÂ§êÂµes:**

- Certifique-se de que pelo menos um dos trêÂªs diretêÂ³rios de motores contenha arquivos de relatêÂ³rio `.md`
- A ferramenta de linha de comando e a interface web sêÂ£o independentes entre si e nêÂ£o se afetam mutuamente
- A geraêÂ§êÂ£o de PDF requer instalaêÂ§êÂ£o de dependêÂªncias do sistema, veja a seêÂ§êÂ£o "Instalar DependêÂªncias do Sistema para ExportaêÂ§êÂ£o PDF" acima

**Re-renderizaêÂ§êÂ£o rêÂ¡pida dos resultados mais recentes:**

- `regenerate_latest_html.py` / `regenerate_latest_md.py`: Remonta o Document IR a partir dos JSONs de capêÂ­tulo da execuêÂ§êÂ£o mais recente em `CHAPTER_OUTPUT_DIR` e renderiza diretamente HTML ou Markdown.
- `regenerate_latest_pdf.py`: LêÂª o IR mais recente de `final_reports/ir` e re-exporta o PDF usando grêÂ¡ficos vetoriais SVG.

## ê¢Å¡â¢ê¯Â¸Â ConfiguraêÂ§êÂ£o AvanêÂ§ada (Obsoleta, jêÂ¡ unificada no arquivo .env do diretêÂ³rio raiz do projeto; outros sub-agents herdam automaticamente a configuraêÂ§êÂ£o do diretêÂ³rio raiz)

### Modificar ParêÂ¢metros-Chave

#### ParêÂ¢metros de ConfiguraêÂ§êÂ£o dos Agents

Cada Agent possui um arquivo de configuraêÂ§êÂ£o dedicado que pode ser ajustado conforme a necessidade. Seguem alguns exemplos:

```python
# QueryEngine/utils/config.py
class Config:
    max_reflections = 2           # Rodadas de reflexêÂ£o
    max_search_results = 15       # NêÂºmero mêÂ¡ximo de resultados de busca
    max_content_length = 8000     # Comprimento mêÂ¡ximo do conteêÂºdo

# MediaEngine/utils/config.py
class Config:
    comprehensive_search_limit = 10  # Limite de busca abrangente
    web_search_limit = 15           # Limite de busca web

# InsightEngine/utils/config.py
class Config:
    default_search_topic_globally_limit = 200    # Limite de busca global
    default_get_comments_limit = 500             # Limite de obtenêÂ§êÂ£o de comentêÂ¡rios
    max_search_results_for_llm = 50              # NêÂºmero mêÂ¡ximo de resultados passados ao LLM
```

#### ConfiguraêÂ§êÂ£o do Modelo de AnêÂ¡lise de Sentimento

```python
# InsightEngine/tools/sentiment_analyzer.py
SENTIMENT_CONFIG = {
    'model_type': 'multilingual',     # OpêÂ§êÂµes: 'bert', 'multilingual', 'qwen', etc.
    'confidence_threshold': 0.8,      # Limiar de confianêÂ§a
    'batch_size': 32,                 # Tamanho do lote
    'max_sequence_length': 512,       # Comprimento mêÂ¡ximo da sequêÂªncia
}
```

### Conectar Diferentes Modelos LLM

Suporta qualquer provedor de LLM no formato de chamada OpenAI. Basta preencher os campos KEY, BASE_URL e MODEL_NAME correspondentes em /config.py.

> O que êÂ© o formato de chamada OpenAI? Aqui estêÂ¡ um exemplo simples:
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
>         'content': "Quais novas oportunidades os modelos de raciocêÂ­nio trarêÂ£o ao mercado"}
>    ],
>)
>
>complete_response = response.choices[0].message.content
>print(complete_response)
>```

### Alterar o Modelo de AnêÂ¡lise de Sentimento

O sistema integra diversos mêÂ©todos de anêÂ¡lise de sentimento, que podem ser escolhidos conforme a necessidade:

#### 1. AnêÂ¡lise de Sentimento MultilêÂ­ngue

```bash
cd SentimentAnalysisModel/WeiboMultilingualSentiment
python predict.py --text "This product is amazing!" --lang "en"
```

#### 2. Ajuste Fino do Qwen3 com Poucos ParêÂ¢metros

```bash
cd SentimentAnalysisModel/WeiboSentiment_SmallQwen
python predict_universal.py --text "Este evento foi um grande sucesso"
```

#### 3. Modelo Ajustado Fino Baseado em BERT

```bash
# Usar modelo BERT chinêÂªs
cd SentimentAnalysisModel/WeiboSentiment_Finetuned/BertChinese-Lora
python predict.py --text "Este produto êÂ© realmente muito bom"
```

#### 4. Modelo Ajustado Fino GPT-2 LoRA

```bash
cd SentimentAnalysisModel/WeiboSentiment_Finetuned/GPT2-Lora
python predict.py --text "Hoje nêÂ£o estou me sentindo muito bem"
```

#### 5. MêÂ©todos Tradicionais de Aprendizado de MêÂ¡quina

```bash
cd SentimentAnalysisModel/WeiboSentiment_MachineLearning
python predict.py --model_type "svm" --text "O atendimento precisa melhorar"
```

### Conectar Banco de Dados de NegêÂ³cios Personalizado

#### 1. Modificar ConfiguraêÂ§êÂ£o de ConexêÂ£o com o Banco de Dados

```python
# Adicionar configuraêÂ§êÂ£o do banco de dados de negêÂ³cios em config.py
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
    """Ferramenta de consulta a banco de dados de negêÂ³cios personalizada"""

    def __init__(self):
        self.connection_config = {
            'host': config.BUSINESS_DB_HOST,
            'port': config.BUSINESS_DB_PORT,
            'user': config.BUSINESS_DB_USER,
            'password': config.BUSINESS_DB_PASSWORD,
            'database': config.BUSINESS_DB_NAME,
        }

    def search_business_data(self, query: str, table: str):
        """Consultar dados de negêÂ³cios"""
        # Implemente sua lêÂ³gica de negêÂ³cios
        pass

    def get_customer_feedback(self, product_id: str):
        """Obter dados de feedback de clientes"""
        # Implemente a lêÂ³gica de consulta de feedback de clientes
        pass
```

#### 3. Integrar ao InsightEngine

```python
# Integrar ferramenta personalizada em InsightEngine/agent.py
from .tools.custom_db_tool import CustomBusinessDBTool

class DeepSearchAgent:
    def __init__(self, config=None):
        # ... outro cêÂ³digo de inicializaêÂ§êÂ£o
        self.custom_db_tool = CustomBusinessDBTool()

    def execute_custom_search(self, query: str):
        """Executar busca personalizada de dados de negêÂ³cios"""
        return self.custom_db_tool.search_business_data(query, "your_table")
```

### Personalizar Templates de RelatêÂ³rio

#### 1. Upload pela Interface Web

O sistema suporta upload de arquivos de template personalizados (formato .md ou .txt), que podem ser selecionados ao gerar relatêÂ³rios.

#### 2. Criar Arquivo de Template

Crie novos templates no diretêÂ³rio `ReportEngine/report_template/`. Nosso Agent selecionarêÂ¡ automaticamente o template mais adequado.

## ê°Å¸Â¤Â Guia de ContribuiêÂ§êÂ£o

Aceitamos contribuiêÂ§êÂµes de todas as formas!

**Por favor, leia o seguinte guia de contribuiêÂ§êÂ£o:**
- [CONTRIBUTING.md](./CONTRIBUTING.md)

## ê°Å¸Â¦â PrêÂ³ximos Passos de Desenvolvimento

Agora o sistema completou a êÂºltima etapa: previsêÂ£o! Acesse e confira [MiroFish - Prever Tudo]: https://github.com/666ghj/MiroFish

<div align="center">
<img src="static/image/MiroFish_logo_compressed.jpeg" alt="banner" width="800">
<img src="static/image/banner_compressed.png" alt="banner" width="800">
</div>

## ê¢Å¡Â ê¯Â¸Â Aviso Legal

**Aviso Importante: Este projeto destina-se exclusivamente a fins de estudo, pesquisa acadêÂªmica e educaêÂ§êÂ£o**

1. **DeclaraêÂ§êÂ£o de Conformidade**:
   - Todo o cêÂ³digo, ferramentas e funcionalidades deste projeto destinam-se exclusivamente a fins de estudo, pesquisa acadêÂªmica e educaêÂ§êÂ£o
   - êâ° estritamente proibido usar este projeto para qualquer finalidade comercial ou atividade lucrativa
   - êâ° estritamente proibido usar este projeto para qualquer comportamento ilegal, irregular ou que viole os direitos de terceiros

2. **IsenêÂ§êÂ£o de Responsabilidade sobre Crawlers**:
   - As funcionalidades de crawler neste projeto destinam-se exclusivamente a fins de aprendizado têÂ©cnico e pesquisa
   - Os usuêÂ¡rios devem respeitar o protocolo robots.txt e os termos de uso dos sites-alvo
   - Os usuêÂ¡rios devem cumprir as leis e regulamentos aplicêÂ¡veis, nêÂ£o realizar coleta maliciosa ou uso indevido de dados
   - Quaisquer consequêÂªncias legais decorrentes do uso das funcionalidades de crawler sêÂ£o de responsabilidade exclusiva do usuêÂ¡rio

3. **IsenêÂ§êÂ£o de Responsabilidade sobre Uso de Dados**:
   - As funcionalidades de anêÂ¡lise de dados do projeto destinam-se exclusivamente a pesquisa acadêÂªmica
   - êâ° estritamente proibido usar os resultados da anêÂ¡lise para decisêÂµes comerciais ou fins lucrativos
   - Os usuêÂ¡rios devem garantir a legalidade e conformidade dos dados analisados

4. **IsenêÂ§êÂ£o de Responsabilidade TêÂ©cnica**:
   - Este projeto êÂ© fornecido "como estêÂ¡", sem qualquer garantia expressa ou implêÂ­cita
   - Os autores nêÂ£o se responsabilizam por quaisquer perdas diretas ou indiretas causadas pelo uso deste projeto
   - Os usuêÂ¡rios devem avaliar por conta prêÂ³pria a adequaêÂ§êÂ£o e os riscos do projeto

5. **LimitaêÂ§êÂ£o de Responsabilidade**:
   - Os usuêÂ¡rios devem compreender plenamente as leis e regulamentos aplicêÂ¡veis antes de usar este projeto
   - Os usuêÂ¡rios devem garantir que seu uso esteja em conformidade com as leis e regulamentos locais
   - Quaisquer consequêÂªncias decorrentes do uso deste projeto em violaêÂ§êÂ£o de leis e regulamentos sêÂ£o de responsabilidade exclusiva do usuêÂ¡rio

**Por favor, leia e compreenda cuidadosamente o aviso legal acima antes de usar este projeto. O uso deste projeto indica que vocêÂª concorda e aceita todos os termos acima.**

## ê°Å¸ââ LicenêÂ§a

Este projeto êÂ© licenciado sob a [LicenêÂ§a GPL-2.0](LICENSE). Para informaêÂ§êÂµes detalhadas, consulte o arquivo LICENSE.

## ê°Å¸Å½â° Suporte e Contato

### Obter Ajuda

Perguntas frequentes: https://github.com/666ghj/BettaFish/issues/185

- **PêÂ¡gina do Projeto**: [RepositêÂ³rio GitHub](https://github.com/666ghj/BettaFish)
- **Reportar Problemas**: [PêÂ¡gina de Issues](https://github.com/666ghj/BettaFish/issues)
- **SugestêÂµes de Funcionalidades**: [PêÂ¡gina de Discussions](https://github.com/666ghj/BettaFish/discussions)

### InformaêÂ§êÂµes de Contato

- **E-mail**: hangjiang@bupt.edu.cn

### CooperaêÂ§êÂ£o Empresarial

- **Desenvolvimento personalizado para empresas**
- **ServiêÂ§os de Big Data**
- **CooperaêÂ§êÂ£o acadêÂªmica**
- **Treinamento têÂ©cnico**

## ê°Å¸âÂ¥ Contribuidores

Agradecemos aos seguintes excelentes contribuidores:

[![Contributors](https://contrib.rocks/image?repo=666ghj/BettaFish)](https://github.com/666ghj/BettaFish/graphs/contributors)

## ê°Å¸ÅÅ¸ Junte-se ao Grupo Oficial de ComunicaêÂ§êÂ£o

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=Bem-vindo ao nosso grupo de comunicaêÂ§êÂ£o têÂ©cnica no QQ!&fontSize=40&fontAlignY=35&desc=Escaneie o QR code abaixo para entrar no grupo&descAlignY=55" alt="Bem-vindo ao nosso grupo de comunicaêÂ§êÂ£o têÂ©cnica no QQ!" style="width:60%; max-width:900px; display:block; margin:0 auto;">
  <img src="static/image/QQ_Light_Horizenal.png" alt="QR code do grupo de comunicaêÂ§êÂ£o têÂ©cnica BettaFish" style="width:60%; max-width:360px; display:block; margin:20px auto 0;">
</div>

## ê°Å¸âÂ¥ê¯Â¸Â Infraestrutura para Deploy

### OpêÂ§êÂ£o Recomendada: Docker Compose

```bash
docker compose up -d
```

Sobe dois containers: a **aplicaêÂ§êÂ£o** + **PostgreSQL 15**.

### Servidor MêÂ­nimo

| Recurso | MêÂ­nimo | Recomendado |
|---------|--------|-------------|
| RAM | 2 GB | 4 GB+ |
| Disco | 5 GB | 10 GB+ |
| CPU | 2 cores | 4+ cores |
| Python | 3.9+ | 3.11 |
| SO | Linux/macOS/Windows | Linux (Ubuntu) |

### Portas Expostas

| Porta | ServiêÂ§o |
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

O sistema usa 6 endpoints de LLM separados, cada um otimizado para sua funêÂ§êÂ£o:

| ServiêÂ§o | FunêÂ§êÂ£o | Modelo Recomendado | Por que um modelo separado? |
|---------|--------|--------------------|-----------------------------|
| Moonshot Kimi | Insight Engine | kimi-k2 | Contexto longo para analisar grandes volumes de dados |
| Gemini 2.5 Pro | Media + Report Engine | gemini-2.5-pro | Multimodal (entende imagens e vêÂ­deos) |
| DeepSeek | Query Engine | deepseek-chat | RêÂ¡pido e barato para muitas buscas web |
| Qwen | Forum Host + Keyword Optimizer | qwen-plus | Tarefas leves de moderaêÂ§êÂ£o e otimizaêÂ§êÂ£o de queries |

Buscadores web (pelo menos um obrigatêÂ³rio):

| ServiêÂ§o | Tipo |
|---------|------|
| Tavily | Busca web |
| Anspire | Busca IA |
| Bocha | Busca IA (alternativa) |

> **Posso usar apenas uma LLM?** Sim! Todas as APIs usam formato OpenAI-compatible. VocêÂª pode apontar todas as 6 variêÂ¡veis no `.env` para o **mesmo modelo** (ex: GPT-4o, Claude ou Gemini), basta repetir a mesma chave/URL/modelo. A separaêÂ§êÂ£o existe para otimizar **custo e desempenho** ê¢â¬â modelos baratos onde pode, modelos fortes onde precisa ê¢â¬â mas funciona perfeitamente com um sêÂ³.

### ConfiguraêÂ§êÂ£o

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

## ê°Å¸âÂ° Custo por RelatêÂ³rio

Cada relatêÂ³rio consome ~620K tokens. Comparativo de custo e velocidade:

| Modelo | Custo/relatêÂ³rio | Tempo | 100 relatêÂ³rios/mêÂªs |
|--------|----------------|-------|---------------------|
| Ollama local (qwen2.5:32b) | $0.00 | 3-4 horas | $0 |
| DeepSeek Chat | $0.11 | 8-12 min | ~$11 |
| GPT-4o-mini | $0.17 | 5-8 min | ~$17 |
| Claude Haiku 3.5 | $1.10 | 8-12 min | ~$110 |
| GPT-4o | $2.98 | 10-15 min | ~$298 |
| Claude Sonnet 4 | $4.14 | 10-15 min | ~$414 |

> Todos os modelos usam formato OpenAI-compatible. Basta trocar `API_KEY`, `BASE_URL` e `MODEL_NAME` no `.env`. Pode usar modelos diferentes por engine. Detalhes completos no [RelatêÂ³rio do Projeto](./RELATORIO_PROJETO.md#8-custo-de-tokens-e-comparativo-de-llms).

## ê°Å¸âË EstatêÂ­sticas do Projeto

<a href="https://www.star-history.com/#666ghj/BettaFish&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=666ghj/BettaFish&type=date&legend=top-left" />
 </picture>
</a>

![Alt](https://repobeats.axiom.co/api/embed/e04e3eea4674edc39c148a7845c8d09c1b7b1922.svg "Repobeats analytics image")

---

Projeto adaptado da comunidade ARCKHê TDS - ARCKHÉe