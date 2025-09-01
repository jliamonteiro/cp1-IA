# Análise de Consumo Elétrico Residencial

## Visão Geral do Projeto

Este projeto realiza uma análise abrangente do consumo elétrico residencial utilizando o dataset "Individual Household Electric Power Consumption" disponível no UCI Machine Learning Repository. O estudo abrange desde a exploração inicial dos dados até aplicações avançadas de machine learning, com o objetivo de identificar padrões de consumo, desenvolver modelos preditivos e fornecer insights sobre o comportamento energético residencial.

## Equipe
- **Julia Monteiro** - RM: 557023
- **Lucas de Assis Fialho** - RM: 557884
- **Sofia Andrade Petruk** - RM: 556585

## Objetivos
- Analisar padrões temporais de consumo elétrico
- Identificar fatores que influenciam o consumo energético
- Desenvolver modelos de machine learning para previsão e classificação
- Fornecer insights sobre eficiência energética residencial
- Demonstrar técnicas avançadas de análise de dados

## Metodologia e Análises Realizadas

### 1. **Preparação e Exploração dos Dados**
- **Carregamento e Estruturação:** Importação do dataset `household_power_consumption.txt` com mais de 2 milhões de registros
- **Análise Exploratória Inicial:** Exame da estrutura dos dados, tipos de variáveis e estatísticas descritivas
- **Tratamento de Dados:** Limpeza de valores ausentes, conversão de tipos de dados e validação da integridade dos dados
- **Características do Dataset:**
  - Período: Dezembro 2006 a Novembro 2010
  - Frequência: Medições a cada minuto
  - Variáveis principais: Potência ativa, reativa, voltagem, intensidade global e sub-medidores

### 2. **Engenharia de Features**
- **Processamento Temporal:** Criação de variáveis de data e hora a partir dos campos originais
- **Features Derivadas:**
  - `Datetime`: Timestamp combinando data e hora
  - `Day_of_week`: Dia da semana (0=Segunda, 6=Domingo)
  - `Month`: Mês do ano
  - `Day_type`: Classificação em dia útil vs. fim de semana
- **Categorização:** Transformação de variáveis contínuas em categorias discretas

### 3. **Análise Temporal**
- **Consumo Diário:** Agregação de dados em médias diárias de potência ativa global
- **Consumo Mensal:** Identificação de padrões sazonais e variações mensais
- **Análise de Pico:** Identificação do dia com maior consumo médio (23/12/2006 com 3.315W)
- **Comparação Semanal:** Análise estatística entre consumo em dias úteis vs. fins de semana
- **Tendências:** Visualização de séries temporais e identificação de padrões de longo prazo

### 4. **Análise de Correlação**
- **Matriz de Correlação:** Análise das relações lineares entre todas as variáveis numéricas
- **Identificação de Dependências:** Correlações fortes entre potência ativa, intensidade global e sub-medidores
- **Análise de Multicolinearidade:** Detecção de variáveis altamente correlacionadas
- **Insights sobre Consumo:** Relações entre diferentes aspectos do consumo elétrico

### 5. **Análise de Sub-medição**
- **Cálculo do Total:** Soma das três sub-medidas (`Sub_metering_1`, `Sub_metering_2`, `Sub_metering_3`)
- **Comparação Mensal:** Análise comparativa entre consumo total de sub-medidores e potência ativa global
- **Detecção de Anomalias:** Identificação de meses com discrepâncias significativas entre medições
- **Distribuição de Consumo:** Análise da contribuição de cada sub-medidor para o consumo total

### 6. **Visualizações Exploratórias**
- **Séries Temporais:** Gráficos de variação diária e mensal da potência ativa
- **Análise de Voltagem:** Distribuição temporal da voltagem em 2008
- **Histogramas:** Distribuições de frequência para variáveis principais
- **Gráficos Comparativos:** Tendências e padrões visuais do consumo energético
- **Análise de Concentração:** Identificação de faixas de voltagem mais frequentes (240-245V)

### 7. **Amostragem e Pré-processamento**
- **Técnicas de Amostragem:** Implementação de amostragem aleatória (1%) para datasets grandes
- **Comparação Estatística:** Validação da representatividade da amostra em relação à população
- **Min-Max Scaling:** Normalização de variáveis numéricas para algoritmos de machine learning
- **Tratamento de Outliers:** Identificação e tratamento de valores extremos

### 8. **Machine Learning**

#### **Clustering (K-Means)**
- **Segmentação:** Aplicação do algoritmo K-Means para agrupar padrões de consumo
- **Otimização:** Método do cotovelo para determinar o número ideal de clusters
- **Interpretação dos Clusters:**
  - **Cluster 0:** Consumo baixo - Períodos de baixo uso energético
  - **Cluster 1:** Consumo médio - Níveis moderados de consumo
  - **Cluster 2:** Consumo alto - Períodos de pico de utilização
- **Análise Temporal:** Distribuição dos clusters ao longo do tempo

#### **Regressão Linear**
- **Modelo Simples:** `Global_active_power` ~ `Global_intensity`
- **Regressão Múltipla:** Inclusão de múltiplas variáveis preditoras
- **Regressão Polinomial:** Captura de relações não-lineares (grau 2)
- **Avaliação de Performance:**
  - Erro Quadrático Médio (RMSE): 0.0852 (múltipla), 0.9691 (simples), 0.9648 (polinomial)
  - R² Score: Medição da variância explicada pelo modelo

#### **Classificação**
- **Random Forest Classifier:** Classificação de alto vs. baixo consumo
- **Regressão Logística:** Modelo alternativo para classificação binária
- **Métricas de Avaliação:** Acurácia, precisão, recall e F1-score
- **Matriz de Confusão:** Análise de erros de classificação

### 9. **Decomposição de Séries Temporais**
- **Modelo Aditivo:** Separação da série temporal em componentes
- **Componentes Analisados:**
  - **Tendência:** Padrões de longo prazo e crescimento/decrescimento
  - **Sazonalidade:** Padrões recorrentes semanais
  - **Resíduos:** Variações não explicadas pelos componentes anteriores
- **Análise Individual:** Interpretação de cada componente separadamente
- **Insights Temporais:** Identificação de padrões cíclicos no consumo

### 10. **Análise de Energia (Dataset Adicional)**
- **Aplicação de K-Means:** Clustering baseado em consumo de eletrodomésticos
- **Análise de Perfil:** Caracterização dos clusters de consumo
- **Correlação Ambiental:** Relações entre consumo e condições ambientais
- **Visualizações Avançadas:** Scatter plots e heatmaps para múltiplas variáveis

## Tecnologias Utilizadas

### Linguagens e Bibliotecas
- **Python 3.7+** - Linguagem principal
- **Pandas** - Manipulação e análise de dados
- **NumPy** - Computação numérica
- **Matplotlib** - Visualizações básicas
- **Seaborn** - Visualizações estatísticas avançadas
- **Scikit-learn** - Machine Learning
- **Statsmodels** - Análise estatística

### Ambiente de Desenvolvimento
- **Jupyter Notebook** - Ambiente interativo de desenvolvimento
- **Google Colab** - Plataforma de execução na nuvem
- **Git** - Controle de versão

## Estrutura do Projeto

```
cp1-IA/
├── individual+household+electric+power+consumption (1)/
│   ├── cp1.ipynb                 # Notebook principal com todas as análises
│   └── household_power_consumption.txt  # Dataset principal
├── energydata_complete.csv       # Dataset adicional para análises avançadas
├── individual+household+electric+power+consumption (1).zip
└── README.md                     # Documentação do projeto
```

## Como Executar

### Pré-requisitos
1. Python 3.7 ou superior instalado
2. Ambiente Jupyter Notebook ou Google Colab
3. Pelo menos 4GB de RAM (recomendado 8GB+ devido ao tamanho do dataset)

### Instalação das Dependências
```bash
# Criar ambiente virtual (recomendado)
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows

# Instalar dependências
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter
```

### Execução Passo a Passo
1. **Clone ou baixe o repositório:**
   ```bash
   git clone <url-do-repositorio>
   cd cp1-IA
   ```

2. **Prepare os dados:**
   - Descompacte o arquivo ZIP se necessário
   - Certifique-se de que `household_power_consumption.txt` está no diretório correto

3. **Execute o notebook:**
   ```bash
   jupyter notebook
   # ou abra cp1.ipynb no Google Colab
   ```

4. **Siga a sequência de execução:**
   - Execute as células em ordem sequencial
   - Cada seção está documentada com explicações detalhadas
   - As análises são progressivas, desde exploração básica até machine learning avançado

## Resultados Principais

### Insights sobre Consumo
- **Padrões Temporais:** Consumo mais elevado durante períodos noturnos e fins de semana
- **Eficiência Energética:** Identificação de períodos de baixo consumo para otimização
- **Correlações:** Forte relação entre potência ativa e intensidade global
- **Clusters:** Três perfis distintos de consumo residencial identificados

### Performance dos Modelos
- **Regressão Linear:** RMSE = 0.0852, bom para previsões básicas
- **Random Forest:** Acurácia = 90%, eficiente para classificação
- **Clustering:** Três clusters bem definidos com perfis distintos

## Conclusões

Este projeto demonstrou uma abordagem completa para análise de consumo elétrico residencial, desde a exploração inicial até aplicações avançadas de machine learning. Os resultados fornecem insights valiosos sobre padrões de consumo e podem ser utilizados para:

- Otimização de consumo energético
- Desenvolvimento de sistemas de monitoramento inteligente
- Previsão de demanda elétrica
- Recomendações de eficiência energética
- Estudos de comportamento do consumidor

## Licença

Este projeto é parte de um trabalho acadêmico e está disponível para fins educacionais.
