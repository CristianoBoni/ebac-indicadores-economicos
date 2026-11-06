# Indicadores econômicos — projeto EBAC / Semantix

Estudo de renda real, inflação e desemprego em 217 economias entre 2000 e 2024, com dados públicos do Banco Mundial. Autor: Cristiano Boni.

## Problema
Como acompanhar a evolução desses indicadores e identificar diferenças entre economias sem confundir médias de países com indicadores ponderados da população mundial?

## Entregas
- `analise_indicadores.ipynb`: seleção das fontes, cruzamento das tabelas, tratamento, colunas derivadas, validações e análises exploratórias com saídas executadas.
- `relatorio_analitico.pdf`: relatório com cinco páginas, resultados, recomendações e limitações.
- `painel_interativo.html`: painel local com seis visualizações e filtros. Abra o arquivo no navegador.
- `wb_gdp.csv`, `wb_inflation.csv`, `wb_unemployment.csv`, `economias.csv` e `painel_indicadores.csv/.parquet`: tabelas de indicadores, dimensão de economias e base consolidada.
- `dados_brutos/`: respostas públicas preservadas da coleta, para rastreabilidade.
- `graficos/`: figuras usadas no relatório.

## Reprodução
Com Python 3.11+, instale as dependências de requirements.txt e abra o notebook no Jupyter ou VS Code. As fontes e os caminhos estão documentados no notebook. A base consolidada é uma fotografia da coleta, não um serviço de atualização automática. Nenhuma chave, senha ou arquivo de credenciais acompanha o projeto.

## Principais achados e limites
O relatório compara distribuição da inflação, média e mediana entre economias, dispersão e correlação entre renda e desemprego, evolução do Brasil e variações de desemprego. Ausências não são convertidas em zero; valores agregados do Banco Mundial são excluídos do painel de economias. As associações são exploratórias e não demonstram causalidade.

## Estado da entrega acadêmica
O painel HTML é uma versão local para revisão. **O dashboard obrigatório no Looker Studio ainda precisa ser finalizado e vinculado aqui antes da submissão.** A publicação de código não equivale à aprovação do projeto pelos tutores.

Fontes: [API do Banco Mundial](https://datahelpdesk.worldbank.org/knowledgebase/topics/125589-developer-information), indicadores NY.GDP.PCAP.KD, SL.UEM.TOTL.ZS e FP.CPI.TOTL.ZG.
