# Trabalho Prático Final — Fundamentos em Ciências de Dados

Análise do impacto demográfico e da evolução temporal da mortalidade durante a pandemia de COVID-19 no Brasil, com foco em três eixos: heterogeneidade regional na incidência e na letalidade, efeito do porte populacional dos municípios e indícios de subnotificação de óbitos por COVID-19 a partir da comparação com mortes por causas respiratórias (SRAG, pneumonia, insuficiência respiratória).

## Arquivo principal

[`Trabalho_Pratico_Fundamentos.ipynb`](./Trabalho_Pratico_Fundamentos.ipynb) é o notebook final entregue, contendo:

1. Descrição do problema e dos dados
2. Preparação dos dados
3. Análise exploratória (5 perguntas, com gráficos de barras, boxplot, dispersão e série temporal)
4. Resultados e conclusões (com relação a estudos publicados sobre a pandemia no Brasil)
5. Fontes utilizadas

## Estrutura do repositório

```
.
├── Trabalho_Pratico_Fundamentos.ipynb   # Notebook final (entrega)
└── Dataset Covid/
    └── extract/                                             # Dados brutos
```

## Dados

Os dados usados neste trabalho vêm do projeto colaborativo [Brasil.io](https://brasil.io/dataset/covid19/files/), que padroniza boletins das Secretarias Estaduais de Saúde e registros de óbito do Registro Civil (cartórios). Os arquivos **não estão neste repositório** porque são pesados (a base `caso_full` sozinha passa de 400 MB descompactada) — eles são ignorados via `.gitignore` e devem ser baixados separadamente.

**Como reproduzir:**

1. Baixe os quatro arquivos compactados em https://brasil.io/dataset/covid19/files/:
   - `boletim.csv.gz`
   - `caso.csv.gz`
   - `caso_full.csv.gz`
   - `obito_cartorio.csv.gz`
2. O notebook principal roda no Google Colab e monta o Google Drive; coloque os arquivos em `MyDrive/` na raiz do seu Drive (é o caminho lido pela célula de carga de dados: `/content/drive/MyDrive/...`).
3. Execute o notebook do início — a primeira célula faz `drive.mount('/content/drive')`.

Alternativamente, a API pública do Brasil.io (https://brasil.io/api/dataset/covid19/) e sua [documentação técnica](https://github.com/turicas/covid19-br/blob/master/api.md) permitem consumir os dados programaticamente.

## Ferramentas

Python 3, `pandas`, `NumPy`, `Matplotlib`, `Seaborn`, executado em Google Colaboratory.

## Referências citadas nas conclusões

- CASTRO, M. C. et al. Spatiotemporal pattern of COVID-19 spread in Brazil. *Science*, v. 372, n. 6544, p. 821–826, 2021. https://www.science.org/doi/10.1126/science.abh1558
- RANZANI, O. T. et al. Characterisation of the first 250 000 hospital admissions for COVID-19 in Brazil. *The Lancet Respiratory Medicine*, v. 9, n. 4, p. 407–418, 2021. https://www.thelancet.com/journals/lanres/article/PIIS2213-2600(20)30560-9/fulltext
- ORELLANA, J. D. Y. et al. Excesso de mortes durante a pandemia de COVID-19: subnotificação e desigualdades regionais no Brasil. *Cadernos de Saúde Pública*, v. 37, n. 1, e00259120, 2021. https://www.scielo.br/j/csp/a/TjDnrpmQBftqgNhtXYPL4Kx/?format=html&lang=pt
- FRANÇA, E. B. et al. Óbitos por COVID-19 no Brasil: quantos e quais estamos identificando? *Revista Brasileira de Epidemiologia*, v. 23, e200053, 2020. https://www.scielosp.org/article/rbepid/2020.v23/e200053/en/
