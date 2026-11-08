# Indicadores econômicos: projeto EBAC e Semantix

Estudo de PIB real por habitante, inflação e desemprego em 217 economias, de 2000 a 2024. Autor: Cristiano Boni.

## Problema e relevância

Como acompanhar renda, emprego e preços para identificar diferenças entre economias sem confundir médias de países com resultados ponderados da população mundial? A análise apoia o acompanhamento de conjuntura e a definição de perguntas para políticas de emprego e estabilidade de preços. Não estima efeitos causais nem fornece previsão.

## Coleta e fontes

Dados públicos estruturados coletados pela API do Banco Mundial (World Development Indicators): NY.GDP.PCAP.KD, PIB per capita em US$ constantes de 2015; SL.UEM.TOTL.ZS, desemprego como porcentagem da força de trabalho; FP.CPI.TOTL.ZG, inflação anual dos preços ao consumidor. A dimensão de economias fornece região, faixa de renda e localização. As respostas originais estão em `dados_brutos/` e o método completo no notebook.

Fontes: https://data.worldbank.org/indicator/NY.GDP.PCAP.KD ; https://data.worldbank.org/indicator/SL.UEM.TOTL.ZS ; https://data.worldbank.org/indicator/FP.CPI.TOTL.ZG ; https://datahelpdesk.worldbank.org/knowledgebase/topics/125589-developer-information

## Modelagem e tratamento

As três tabelas de indicadores têm 5.425 linhas e 11 colunas cada. O cruzamento usa economia ISO3 e ano. A base consolidada possui 5.425 registros, 15 colunas e datas de referência anuais. As duas colunas derivadas são crescimento anual do PIB real per capita (%) e variação anual do desemprego em pontos percentuais. Agregados regionais fornecidos pelo Banco Mundial são excluídos da população de economias. Ausências são preservadas, com exclusão por análise e cobertura documentada. Médias internacionais não são ponderadas por população.

## EDA e conclusões

O notebook executado e o relatório de cinco páginas apresentam cobertura dos indicadores, trajetória brasileira, distribuição da inflação, correlações e dispersão de renda/desemprego, medianas por região e variações do desemprego.

Em 2024, a inflação apresenta média de 7,41% e mediana de 3,01% em 176 economias com dados, indicando influência de valores extremos. O Brasil apresenta PIB real per capita de US$ 9.566,75 (2015), desemprego de 6,80% e inflação de 4,37%. A correlação exploratória não sustenta inferir causalidade entre renda e desemprego.

Para o acompanhamento, priorizar medianas e distribuições além da média, verificar cobertura e investigar economias com movimentos extremos antes de propor intervenções. Comparações devem considerar estruturas de mercado de trabalho, métodos de medição e diferenças de renda.

## Dashboard no Looker Studio

https://datastudio.google.com/reporting/934e2f93-8684-431c-b6bc-8bbcb2973b80

A primeira página contém tabela conectada à base completa, filtrável por economia (ISO3) e ano, inicialmente no Brasil. PIB, inflação e desemprego usam agregação por média. A segunda página apresenta seis visualizações fixas da análise com interpretação. Os filtros da primeira página não alteram as figuras da segunda página.

O acesso do relatório é de leitura por link, sem indexação pública. O painel é uma fotografia da coleta de 2000 a 2024, sem atualização automática.

## Arquivos e reprodução

- `analise_indicadores.ipynb`: análise executada, validações, limpeza e cálculos.
- `relatorio_analitico.pdf`: problema, fontes, achados e limitações.
- `wb_gdp.csv`, `wb_inflation.csv`, `wb_unemployment.csv`, `economias.csv`: tabelas de origem.
- `painel_indicadores.csv` e `.parquet`: base consolidada.
- `dados_brutos/`: respostas públicas originais.
- `graficos/`: figuras do relatório.
- `painel_interativo.html`: painel local adicional, com filtros próprios.
- `indicadores_looker.xlsx`: conversão da base para o conector Excel do Looker Studio.
- `graficos_painel.png`: seis gráficos apresentados na segunda página.

Instalar `requirements.txt` em Python 3.11+ e executar o notebook em Jupyter ou VS Code. O pacote anexado à EBAC oferece os arquivos completos ao tutor mesmo que ele não tenha acesso ao repositório privado. A entrega aguarda avaliação acadêmica.
