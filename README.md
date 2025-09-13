# Análise e Predição de Geração de Energia Solar

Este projeto utiliza um conjunto de dados de geração de energia para realizar uma análise completa, desde a limpeza e organização dos dados até o treinamento de um modelo de machine learning para prever a potência de geração (`Power(W)`).

O processo é desenvolvido em um notebook Jupyter e inclui etapas de extração de dados, transformação, engenharia de features e modelagem preditiva.

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Jairzaoo/ProjetoIntegrador/blob/main/Projeto_integrador.ipynb)

---

## 🚀 Sobre o Projeto

O objetivo principal é analisar dados históricos de um sistema de geração de energia e construir um modelo de regressão capaz de prever a potência gerada em um determinado momento. O notebook automatiza todo o fluxo de trabalho:

1.  **Extração e Ordenação**: Os dados são lidos de uma URL pública do Google Drive, convertidos para um formato de data e hora adequado e ordenados cronologicamente.
2.  **Limpeza e Engenharia de Features**:
    - A coluna `Working Mode` é removida.
    - A coluna de tempo (`Time`) é decomposta em features numéricas: `Ano`, `Mês`, `Dia`, `Hora` e `Minuto`.
    - As colunas são renomeadas para facilitar o entendimento.
3.  **Treinamento do Modelo de Machine Learning**:
    - Um modelo `RandomForestRegressor` é treinado para prever a `Power(W)`.
    - As features utilizadas para o treinamento são: `Ano`, `Mês`, `Dia`, `Hora`, `Minuto` e `Geracao Total(kWh)`.
4.  **Avaliação e Persistência**:
    - O modelo é avaliado utilizando métricas como Erro Absoluto Médio (MAE) e R².
    - O modelo treinado é salvo no arquivo `modelo_predicao_potencia.joblib` para que possa ser reutilizado sem a necessidade de um novo treinamento.

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Python
- **Bibliotecas Principais**:
  - **Pandas**: Para manipulação e análise de dados.
  - **Scikit-learn**: Para o treinamento e avaliação do modelo de machine learning.
  - **Joblib**: Para salvar e carregar o modelo treinado.
- **Ambiente**: Jupyter Notebook / Google Colab

## 📈 Como Executar

A maneira mais simples de executar este projeto é através do Google Colab.

1.  Clique no botão "Abrir no Colab" no topo deste README.
2.  No ambiente do Colab, execute as células sequencialmente clicando em "Ambiente de execução" > "Executar tudo".

O notebook irá gerar os seguintes arquivos no ambiente de execução:
- `dados_consolidados_ordenados.csv`: Dados brutos após a ordenação.
- `dados_limpos.csv`: Dados prontos para o treinamento do modelo.
- `modelo_predicao_potencia.joblib`: O arquivo com o modelo de regressão treinado.

## 📂 Estrutura do Notebook

O notebook está dividido nas seguintes seções:

1.  **Ordenação dos Dados**: Carrega os dados da fonte original e os organiza por data.
2.  **Processamento e Limpeza**: Remove colunas, trata formatos e extrai novas features de tempo.
3.  **Treinamento do Modelo**: Prepara os dados, separa em conjuntos de treino/teste, treina o `RandomForestRegressor` e avalia sua performance.
4.  **Previsão e Salvamento**: Demonstra como usar o modelo para fazer previsões e o salva em um arquivo.
