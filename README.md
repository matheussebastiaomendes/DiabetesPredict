
# Modelo Preditivo para diagnóstico de diabetes 

Os dados podem ser encontrados no [Kaggle](https://www.kaggle.com/datasets/priyamchoksi/100000-diabetes-clinical-dataset) e foram disponibilizados por [Priyam Choksi](https://www.kaggle.com/priyamchoksi).

# DiabetesPredict

A diabetes é uma condição crônica que afeta a forma como o corpo metaboliza a glicose, um tipo de açúcar que serve como principal fonte de energia. Existem diferentes tipos de diabetes, sendo os mais comuns o tipo 1 e o tipo 2. No diabetes tipo 1, o corpo não produz insulina, o hormônio responsável por regular os níveis de açúcar no sangue. Já no tipo 2, o corpo não utiliza a insulina de maneira eficaz ou não produz insulina suficiente.


![](foto)

### Objetivos e resultados

O primeiro objetivo é responder às seguintes perguntas sobre o dataset:

- Qual é a predominância de diabetes entre os gêneros?
- Qual a probabilidade de cada gênero ter diabetes?
- Como está a distribuição das informações fumantes por idade?
- O gênero impacta no nivel de glicose no sangue?


### 🛠️ Ferramentas utilizadas
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## A estrutura do dataset

As colunas do dataset estão organizadas da seguinte forma:

| Coluna                       | Descrição                                                       |
|------------------------------|-----------------------------------------------------------------|
| year                         | Ano em que os dados foram recolhidos                            |
| gender                       | Género da pessoa (por exemplo, "masculino" ou "feminino").      |                          
| age          		             | Idade da pessoa (em anos)                                       |
| location                     | Localização geográfica                                          |
| race:AfricanAmerican         | Pessoa se identifica como afro-americana (1 = Sim, 0 = Não)     |                          
| race:Asian           	       | Pessoa se identifica como asiática (1 = Sim, 0 = Não)           |
| race:Caucasian               | Pessoa se identifica como caucasiana (1 = Sim, 0 = Não)         |
| race:Hispanic                | Pessoa se identifica como hispânica (1 = Sim, 0 = Não).         |
| race:Other                   | Pessoa se identifica como outra raça (1 = Sim, 0 = Não)         |                          
| hypertension                 | Indica se a pessoa tem hipertensão (1 = Sim, 0 = Não)		       |
| heart_disease                | Indica se a pessoa tem alguma doença cardíaca(1 = Sim, 0 = Não) |                          
| smoking_history              | Histórico de tabagismo da pessoa                                |
| bmi                	         | Índice de Massa Corporal (IMC)                                  |                    
| hbA1c_level	                 | Nível de hemoglobina glicada (HbA1c                             |
| blood_glucose_level	         | Nível de glicose no sangue no momento da medição                |                          
| diabetes      	             | Indica se a pessoa tem diabetes (1 = Sim, 0 = Não) 		         |


## Bibliotecas utilizadas

#### EDA (Análise Exploratória de Dados)
- Pandas, Numpy.
#### Visualizações Gráficas
- Seaborn, Matplotlib.
#### Machine Learning
- sklearn (scikit-learn)
- xgboost (XGBoost Classifier)

# Análise exploratória de dados 

## Colocar as perguntas e os resultados?

# Modelo de Predição

## Pré-processamento dos dados
As colunas numéricas e categóricas foram separadas e tratadas. As colunas numéricas receberam um imputer de mediana da coluna analisada nos valores faltantes. Além disso, também foi feito Standard Scaler para a padronização dos dados, para ter média zero e variância unitária. Já nas colunas categóricas, utilizamos o OneHotEncoder para sua transformação.

## Balanceamento de classes

Verificamos que a classe minoritária (1 - possui diabetes)  possui uma representatividade quase definirX menor que a classe majoritária (0 - não possui diabetes), esse desbalanceamento pode influenciar no desempenho do modelo, para tratar esse desbalanceamento optei por utilizar um Class Weight

Calculando chegamos no seguinte peso para cada uma das classes:

## Feature selection
Após o tratamento das colunas, utilizamos o Rfe para a seleção das features que têm maior impacto no modelo.

## Random Forest Classifier

Utilizamos os seguintes parametros no modelo

## Métricas
As métricas do modelo 

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |             |
| Precison  |             |
| Recall    |             |
|           |             |

![](https://github.com/matheussebastiaomendes/modelo_predicao/blob/main/imagens/comportamento_modelo_LGBMODEL.png)

## Métricas apuradas após a validação cruzada

A validação cruzada divide o dataset em varias partições os chamados folds, separa partes diferentes dos dados em cada fold para treinamento e validação, a partir dai extraimos as métricas de avaliação de cada treinamento realizado e fazemos uma média dos resultados, nos trazendo uma visão mais realista do real desempenho do modelo.

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |             |
| Precison  |             |
| Recall    |             |
|           |             |

## Xgboost Classifier

Para este modelo, mantivemos o tratamento das colunas numéricas e categóricas e incluímos alguns parâmetros do modelo Xgboost Classifier.

As métricas do modelo 

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |             |
| Precison  |             |
| Recall    |             |
|           |             |

![](https://github.com/matheussebastiaomendes/modelo_predicao/blob/main/imagens/comportamento_modelo_RANDOM_FOREST.png)

## Métricas apuradas após a validação cruzada

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |             |
| Precison  |             |
| Recall    |             |
|           |             |
