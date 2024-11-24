# 📊 Modelo Simples: Otimização de Variáveis com Base Estatística

Este projeto analisa dados de investimentos em marketing e seu impacto nas vendas, utilizando técnicas simples e diretas para criar um modelo preditivo e compreender as relações entre as variáveis. Ele inclui análise exploratória, limpeza de dados e avaliação de métricas, com foco na simplicidade da modelagem para extrair insights significativos. Além disso, técnicas como regularização com **Ridge Regression** e curvas de aprendizagem foram aplicadas, seguindo uma base sólida de conceitos estatísticos e teóricos.

---

## 📌 Objetivos do Projeto
1. Entender a relação entre os investimentos em diferentes plataformas de marketing (YouTube, Facebook e Newspaper) e o número de vendas geradas.
2. Identificar quais variáveis têm maior impacto no resultado.
3. Construir um modelo de regressão linear, incluindo técnicas de regularização para prever vendas com base nos investimentos em marketing.
4. Demonstrar a aplicação de fundamentos estatísticos e teóricos para embasar decisões analíticas.

---

## 📂 Estrutura do Projeto

### **1. Análise Exploratória dos Dados**
- Estatísticas descritivas para entender as distribuições individuais de cada variável, como média, mediana e dispersão.
- Verificação de correlações lineares entre as variáveis explicativas (`youtube`, `facebook`, `newspaper`) e a variável dependente (`sales`) para identificar relações diretas e independentes.
- **Análise de interações entre variáveis explicativas**:
  - Exploramos como os efeitos combinados de variáveis, como `youtube` e `facebook`, poderiam ter impacto sinérgico ou antagônico nas vendas.
  - Utilizamos scatterplots e mapas de calor para identificar padrões de interação.
  - Criamos termos de interação, como `youtube * facebook`, para incluir combinações potencialmente significativas na modelagem.
- **Gráficos para visualização**:
  - Scatter plots entre variáveis explicativas e a variável dependente.
  - Mapas de calor para exibir correlações e identificar potenciais interações.

---

### **2. Modelagem**
- Construção inicial de um modelo de regressão linear utilizando variáveis explicativas para capturar relações diretas entre os investimentos em marketing (`youtube`, `facebook`, `newspaper`) e o retorno em vendas.
  - Utilizamos o método de **Mínimos Quadrados Ordinários (OLS)** para obter uma linha base, identificando o impacto direto de cada variável nas vendas e avaliando a significância estatística dos coeficientes.
- Expansão do modelo com **variáveis polinomiais**, permitindo capturar relações não lineares e interações entre os fatores explicativos. Esse enriquecimento do espaço de variáveis trouxe flexibilidade ao modelo para ajustar padrões complexos nos dados.
- **Ajuste de hiperparâmetros**:
  - Aplicamos validação cruzada (k-fold) para selecionar os melhores valores do parâmetro de regularização (**alpha**) no contexto de **Ridge Regression**, garantindo que o modelo fosse robusto e menos suscetível a overfitting.
  - A validação cruzada avaliou múltiplas combinações de parâmetros, minimizando o erro médio quadrático em subconjuntos dos dados.
- Aplicação de **Ridge Regression**:
  - Incorporamos regularização L2 para reduzir o impacto da multicolinearidade, comum em dados de marketing, estabilizando os coeficientes do modelo.
  - O termo de penalidade controlou coeficientes extremos, resultando em maior generalização nas previsões.
- **Tratamento de heterocedasticidade**:
  - Utilizamos testes estatísticos, como **Breusch-Pagan**, para detectar variâncias inconsistentes nos resíduos.
  - Implementamos transformações logarítmicas para estabilizar a variância nas variáveis explicativas e dependente, tornando os erros mais consistentes.
  - Quando necessário, ajustamos modelos ponderados (**Weighted Least Squares - WLS**) para lidar com a heterocedasticidade residual, atribuindo pesos inversamente proporcionais à variância observada.
- **Avaliação do modelo**:
  - O desempenho foi medido utilizando métricas como:
    - **R² ajustado**: Para avaliar a proporção da variância explicada pelo modelo.
    - **RMSE (Root Mean Square Error)**: Para medir a precisão das previsões.
    - **MAPE (Mean Absolute Percentage Error)**: Para medir o erro percentual médio das previsões em relação aos valores reais.
  - Realizamos análise dos resíduos para garantir a adequação do modelo e detectar padrões não capturados.

---

### **3. Curvas de Aprendizagem**
- Análise de desempenho do modelo à medida que o volume de dados aumenta.
- Identificação de possíveis melhorias na qualidade das previsões.

---

### **4. Resultados**
- Identificação de que a plataforma **YouTube** tem maior impacto nas vendas.
- Previsão precisa das vendas com base nos investimentos.

---

## 🛠️ Tecnologias Utilizadas
- **Linguagem**: Python
- **Bibliotecas**:
  - `pandas` e `numpy`: Manipulação e análise de dados.
  - `matplotlib` e `seaborn`: Visualizações gráficas.
  - `statsmodels` e `sklearn`: Construção e avaliação do modelo, incluindo regularização com Ridge.

---

## 📈 Resultados
### Desempenho do Modelo Ridge (α=0.01)

- **R² (Treino)**: 99.71%
- **R² (Teste)**: 99.54%
- **MSE (Treino)**: 0.0025
- **MSE (Teste)**: 0.0047
- **Validação Cruzada**:
  - R² Médio (K-Fold): **99.60% (±0.0014)**
  - MSE Médio (K-Fold): **0.0033 (±0.0011)**

### Métricas Adicionais
- **Log-Likelihood**:
  - Treino: **198.63**
  - Teste: **40.30**
- **AIC** (Akaike Information Criterion):
  - Treino: **-381.27**
  - Teste: **-64.60**
- **BIC** (Bayesian Information Criterion):
  - Treino: **-358.58**
  - Teste: **-52.87**

### Análise
- O modelo apresentou excelente capacidade de explicação dos dados, com valores de **R² elevados tanto no conjunto de treino quanto no conjunto de teste**.
- A diferença mínima de **0.17% no R²** entre treino e teste demonstra que o modelo está bem ajustado, sem sinais de overfitting ou underfitting.
- As métricas de validação cruzada confirmam a **robustez e consistência do modelo** em diferentes subconjuntos de dados.
- Métricas como AIC e BIC reforçam a eficiência do modelo ao penalizar a complexidade sem sacrificar o desempenho.


---

## 📝 Como Reproduzir
1. Clone este repositório:
   ```bash
   git clone https://github.com/RodrigoCamposDS/modelo-regressao-simples.git
   cd modelo-regressao-simples



