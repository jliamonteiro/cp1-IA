# Análise de Consumo Elétrico Residencial

**Nome:** Julia Monteiro  
**RM:** 557023


## 🔍 Metodologia e Análises Realizadas

### 1. **Preparação e Exploração dos Dados**
- Carregamento do dataset `household_power_consumption.txt`
- Exploração inicial: estrutura, tipos de dados e primeiras observações
- Verificação e tratamento de valores ausentes
- Conversão de tipos de dados apropriados

### 2. **Engenharia de Features**
- **Datetime:** Combinação de data e hora em formato timestamp
- **Day_of_week:** Extração do dia da semana (0=Segunda, 6=Domingo)
- **Month:** Extração do mês
- **Day_type:** Classificação em fim de semana vs. dia de semana

### 3. **Análise Temporal**
- **Consumo Diário:** Cálculo de médias diárias de `Global_active_power`
- **Consumo Mensal:** Agregação por mês para identificar padrões sazonais
- **Dia de Pico:** Identificação do dia com maior consumo médio
- **Análise Semanal:** Comparação estatística entre dias úteis e fins de semana

### 4. **Análise de Correlação**
- Matriz de correlação entre variáveis numéricas principais
- Identificação de relações lineares entre diferentes medições elétricas
- Análise de multicolinearidade entre variáveis

### 5. **Análise de Sub-medição**
- Cálculo do total de sub-medição (soma de `Sub_metering_1`, `Sub_metering_2`, `Sub_metering_3`)
- Comparação mensal entre total de sub-medição e `Global_active_power`
- Identificação de meses com discrepâncias significativas

### 6. **Visualizações Exploratórias**
- **Séries Temporais:** Variação diária de `Global_active_power`
- **Análise de Voltagem:** Gráfico temporal para `Voltage` em 2008
- **Distribuições:** Histograma da distribuição de `Voltage`
- Gráficos comparativos e de tendências

### 7. **Amostragem e Normalização**
- Técnicas de amostragem para datasets grandes
- Comparação de distribuições entre amostra e população
- **Min-Max Scaling:** Normalização de variáveis numéricas para análises posteriores

### 8. **Machine Learning**

#### **Clustering (K-Means)**
- Segmentação em 3 clusters baseados em `Global_active_power`
- Interpretação dos clusters:
  - **Cluster 1:** Consumo baixo
  - **Cluster 2:** Consumo médio
  - **Cluster 3:** Consumo alto
- Análise da distribuição temporal dos clusters

#### **Regressão Linear**
- Modelo preditivo: `Global_active_power` ~ `Global_intensity`
- Avaliação de performance do modelo
- Interpretação dos coeficientes

### 9. **Decomposição de Série Temporal**
- Separação em componentes:
  - **Tendência:** Padrão de longo prazo
  - **Sazonalidade:** Padrões semanais recorrentes
  - **Resíduo:** Variações não explicadas pelos componentes anteriores
- Análise de cada componente individualmente


## 🚀 Como Executar

### **Pré-requisitos:**
1. Python 3.7+ instalado
2. Dataset `household_power_consumption.txt` disponível, ele está em zip pois é muito pesado, então retire do diretório e suba somente o txt

### **Instalação das Dependências:**
```bash
pip install pandas matplotlib seaborn scikit-learn statsmodels numpy
```

### **Execução:**
1. **Clone o repositório** (se aplicável) ou baixe os arquivos
2. **Coloque o dataset** `household_power_consumption.txt` no mesmo diretório do notebook
3. **Abra o notebook** em Jupyter, Google Colab ou outro ambiente compatível
4. **Execute as células sequencialmente** para reproduzir toda a análise





