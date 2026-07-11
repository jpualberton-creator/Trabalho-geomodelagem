# Trabalho: Análise Climatológica Integrada para a Cadeia Produtiva do Açaí no Pará

Este repositório contém o código-fonte, dados e relatórios referentes ao projeto de modelagem ambiental e visão computacional aplicados à cultura do açaí no estado do Pará.

*   `notebooks/`
    *   `Parte1.ipynb`: Notebook do Google Colab focado na extração de dados Copernicus (ERA5-Land) e plotagem de mapas com Cartopy.
    *   `Parte3.ipynb`: Notebook contendo a análise integrada (IBGE/SIDRA + Clima).

*   `outputs/`
    *   `figuras/`: Mapas sazonais gerados (Vento, Temperatura, etc.).
    *   `predicoes/`: Imagens de validação e predições do YOLO.
    *   `tabelas/`: Dados gerados da análise integrada.
*   `relatorio/`
    *   `Relatorio_Final.pdf`: Documento completo contendo metodologia, resultados e conclusões.

Para que a análise funcione corretamente, os notebooks devem ser executados na ordem abaixo devido à dependência de arquivos intermediários:

1-Parte1.ipynb (Gera o arquivo `dados_climaticos_estacoes.csv`)
2-Parte3.ipynb (Lê o arquivo gerado na Parte 1 e cruza com os dados do IBGE)
 Parte 1 - Dados Climáticos (Copernicus)
1. Abra o arquivo `notebooks/Parte1.ipynb` no Google Colab.
2. Certifique-se de configurar sua chave da API do Copernicus (CDS API) na célula indicada.
3. Execute todas as células. O código baixará dados do ERA5-Land para o ano de 2024, converterá as unidades e gerará mapas de vento e temperatura.
4. Ao final, o notebook exportará as médias sazonais diretamente para o seu Google Drive.
 Parte 3 - Análise Integrada
1. Abra o arquivo `notebooks/Parte3.ipynb` no Google Colab.
2. Este notebook consumirá o arquivo `dados_climaticos_estacoes.csv` gerado no Passo 1 e buscará os dados de produção do IBGE via API do SIDRA.
3. Rode todas as células para gerar a matriz de dados agregados por município e os mapas coropléticos de densidade de produção.

---

Ferramentas Utilizadas

  Xarray & NetCDF4: Manipulação de dados meteorológicos em grade.
  Cartopy & Matplotlib: Geração de mapas climatológicos sazonais.
  Geopandas & Geobr: Processamento de malhas geográficas dos municípios do Pará.
