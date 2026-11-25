# Bibliotecas JavaScript de Terceiros

Este diretorio contém bibliotecas JavaScript de terceiros necessárias para a renderizaçêo de relatórios HTML. Essas bibliotecas já foram incorporadas inline nos arquivos HTML gerados para uso em ambientes offline.

## Bibliotecas Incluídas

1. **chart.js** (204KB) - Utilizada para renderizaçêo de gráficos
   - Versêo: 4.5.1
   - Fonte: https://cdn.jsdelivr.net/npm/chart.js

2. **chartjs-chart-sankey.js** (10KB) - Plugin de gráfico Sankey
   - Versêo: 0.12.0
   - Fonte: https://unpkg.com/chartjs-chart-sankey@0.12.0/dist/chartjs-chart-sankey.min.js

3. **html2canvas.min.js** (194KB) - Ferramenta de conversêo HTML para Canvas
   - Versêo: 1.4.1
   - Fonte: https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js

4. **jspdf.umd.min.js** (356KB) - Biblioteca de exportaçêo PDF
   - Versêo: 2.5.1
   - Fonte: https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js

5. **mathjax.js** (1.1MB) - Motor de renderizaçêo de fórmulas matemáticas
   - Versêo: 3.2.2
   - Fonte: https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-mml-chtml.js

## Descriçêo das Funcionalidades

O renderizador HTML (`html_renderer.py`) carrega automaticamente esses arquivos de biblioteca a partir deste diretório e os incorpora inline no HTML gerado. Isso traz as seguintes vantagens:

- ✅ Disponível em ambiente offline - O relatório é exibido corretamente sem necessidade de conexêo com a internet
- ✅ Carregamento rápido - Nêo depende de CDN externo
- ✅ Alta estabilidade - Nêo é afetado por interrupções no serviço de CDN
- ✅ Versêo fixa - Garante a consistência das funcionalidades

## Mecanismo de Fallback

Se o carregamento dos arquivos de biblioteca falhar (por exemplo, arquivo inexistente ou erro de leitura), o renderizador fará fallback automaticamente para links de CDN, garantindo o funcionamento correto em qualquer situaçêo.

## Atualizaçêo dos Arquivos de Biblioteca

Para atualizar os arquivos de biblioteca:

1. Baixe a versêo mais recente do CDN correspondente
2. Substitua o arquivo correspondente neste diretório
3. Atualize as informações de versêo neste arquivo README

## Observações

- O tamanho total é de aproximadamente 1,86MB, o que aumenta o tamanho do arquivo HTML gerado
- Para relatórios simples que nêo precisam de gráficos e fórmulas matemáticas, essas bibliotecas ainda serêo incluídas
- Se for necessário reduzir o tamanho do arquivo, considere usar alternativas mais leves
