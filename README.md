# Modelo-CAPM-Analise-de-Retornos-de-Acoes

# Análise de Risco e Retorno usando o Modelo CAPM e Otimização de Portfólio

Este repositório contém um conjunto de códigos em Python para análise de risco e retorno de ativos financeiros, utilizando o modelo **CAPM** (Capital Asset Pricing Model) e a técnica de **otimização de portfólio**. O objetivo é demonstrar como calcular e visualizar o desempenho de ações e de um portfólio composto por múltiplos ativos.

## O que é o CAPM?

O **CAPM (Capital Asset Pricing Model)** é um modelo amplamente utilizado para determinar o retorno esperado de um ativo com base em seu risco sistemático (beta) em relação ao mercado. A fórmula principal do CAPM é:

\[
E(R_i) = R_f + \beta_i (E(R_m) - R_f)
\]

Onde:
- \(E(R_i)\) é o retorno esperado do ativo \(i\),
- \(R_f\) é a taxa livre de risco,
- \(\beta_i\) é o coeficiente beta do ativo \(i\), que representa sua sensibilidade ao mercado,
- \(E(R_m)\) é o retorno esperado do mercado.

Esse modelo ajuda a entender como o risco de um ativo impacta seu retorno esperado, considerando o comportamento do mercado como um todo.

## Análise de Risco e Retorno

A **Análise de Risco e Retorno** é essencial para avaliar investimentos, relacionando o retorno de um ativo ao risco associado a ele. O risco é frequentemente medido pelo **desvio padrão**, que indica a volatilidade dos retornos, enquanto o **Índice de Sharpe** ajuda a comparar o retorno ajustado pelo risco entre diferentes ativos ou portfólios.

Além disso, a análise permite a construção de uma **fronteira eficiente**, que otimiza a combinação de risco e retorno, ajudando investidores a tomar decisões fundamentadas.

## Implementação

Este repositório contém código em Python para calcular e analisar:

- **Beta** de ativos em relação ao mercado,
- **Retorno esperado** com base no modelo CAPM,
- **Risco e Retorno** de portfólios de ativos,
- **Índice de Sharpe** e outras métricas de risco.

### Objetivos do Projeto:
- **Análise de Retorno e Risco de Ativos**: Avaliar os retornos diários das ações de empresas e comparar com o índice de mercado (IBOVESPA ou S&P 500).
- **Modelo CAPM**: Estimar o retorno esperado de uma ação com base em sua relação com o mercado, utilizando o modelo CAPM.
- **Otimização de Portfólio**: Encontrar a combinação ótima de ativos para maximizar a razão de Sharpe, ou seja, a rentabilidade ajustada ao risco.
- **Visualização de Dados**: Utilizar gráficos interativos para explorar os dados, incluindo a correlação entre ativos e seus preços ajustados.

### Bibliotecas Utilizadas:
O projeto utiliza as seguintes bibliotecas:
- **`yfinance`**: Para obter dados históricos de preços das ações e índices de mercado.
  - Usada para fazer o download de preços ajustados de fechamento de ativos financeiros.
- **`PyPortfolioOpt`**: Para otimização de portfólio, cálculo de retornos esperados e risco.
  - Utilizada para calcular o retorno esperado com base nos dados históricos e para otimizar o portfólio de ativos.
- **`Matplotlib`** e **`Seaborn`**: Para visualização de gráficos estáticos, incluindo a distribuição de retornos e matrizes de correlação.
  - Utilizadas para gerar gráficos estáticos de linha e de dispersão.
- **`Plotly`**: Para gerar gráficos interativos, permitindo exploração dinâmica dos dados.
  - Usada para criar gráficos de preços ajustados e de dispersão interativos entre retornos de ativos.

