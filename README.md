# Modelo-CAPM-Analise-de-Retornos-de-Acoes

# Análise de Risco e Retorno usando o Modelo CAPM e Otimização de Portfólio

Este repositório contém um conjunto de códigos em Python para análise de risco e retorno de ativos financeiros, utilizando o modelo **CAPM** (Capital Asset Pricing Model) e a técnica de **otimização de portfólio**. O objetivo é demonstrar como calcular e visualizar o desempenho de ações e de um portfólio composto por múltiplos ativos.

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

Descrição do Código:
1. Obtendo Dados Históricos com yfinance:
O código começa baixando os preços ajustados de fechamento de um conjunto de ações e índices de mercado, utilizando o yfinance. Exemplo:

python
Copiar código
tickers = ["PETR4.SA", "^BVSP"]  # Ação PETR4 e índice IBOVESPA
data = yf.download(tickers, start="2020-01-01", end="2024-01-01")["Adj Close"]
Esses dados são então usados para calcular os retornos diários e realizar a análise de risco e retorno.

2. Modelo CAPM:
O código aplica o modelo CAPM para estimar o retorno esperado de um ativo com base em sua relação com o mercado. A fórmula básica do CAPM é:

𝑅
𝑖
=
𝑅
𝑓
+
𝛽
𝑖
(
𝑅
𝑚
−
𝑅
𝑓
)
R 
i
​
 =R 
f
​
 +β 
i
​
 (R 
m
​
 −R 
f
​
 )
Onde:

𝑅
𝑖
R 
i
​
  é o retorno esperado do ativo,
𝑅
𝑓
R 
f
​
  é a taxa livre de risco,
𝛽
𝑖
β 
i
​
  é a sensibilidade do ativo ao mercado,
𝑅
𝑚
R 
m
​
  é o retorno esperado do mercado.
A regressão linear é usada para calcular o 
𝛽
𝑖
β 
i
​
  da ação em relação ao índice de mercado, e o R² e coeficientes são analisados para entender a relação entre os ativos e o mercado.

3. Otimização de Portfólio:
Usando a biblioteca PyPortfolioOpt, o código otimiza um portfólio de ativos, calculando os retornos esperados e a matriz de covariância. O objetivo é maximizar a razão de Sharpe:

python
Copiar código
ef = EfficientFrontier(mu, S)
weights = ef.max_sharpe()
Isso retorna a combinação de pesos que gera a melhor rentabilidade ajustada ao risco.

4. Visualizações:
Gráfico de Retornos Diários: O código utiliza Matplotlib e Seaborn para exibir gráficos de retornos diários dos ativos e matrizes de correlação.

python
Copiar código
sns.lineplot(data=returns)
plt.title("Retornos Diários")
plt.show()
Preços Ajustados ao Longo do Tempo: Utiliza Plotly para criar gráficos interativos que permitem visualizar como os preços ajustados dos ativos evoluíram ao longo do tempo.

python
Copiar código
fig = px.line(data_long, x='Date', y='Preço Ajustado', color='Ticker')
fig.show()
Correlação entre Retornos: Calcula a correlação entre os retornos de diferentes ativos e exibe um gráfico de dispersão interativo para visualizar a relação entre eles:

python
Copiar código
fig = px.scatter(returns, x="AAPL", y="MSFT", title="Correlação entre Retornos: AAPL vs MSFT")
fig.show()
