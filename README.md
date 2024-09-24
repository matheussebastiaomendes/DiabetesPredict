# DiabetesPredict
Modelo de machine learning para a predição do de diagnosticos de diabetes

# Modelo Preditivo para preços de veículos 🚗

Neste projeto, será feita uma análise exploratória dos dados e a elaboração de um modelo preditivo utilizando LightGBM e Random Forest. Os dados podem ser encontrados no [Kaggle](https://www.kaggle.com/datasets/hellbuoy/car-price-prediction/data) e foram disponibilizados por [Manish Kumar](https://www.kaggle.com/hellbuoy).

### Problema de negócio

A empresa Toad Motors, especializada na venda de veículos, está buscando entender melhor o mercado de carros que comercializa. A empresa possui um vasto conjunto de dados sobre diferentes marcas e modelos de carros, incluindo informações como preço, potência, consumo urbano, comprimento, largura e tipo de carroceria. O objetivo é usar esses dados para otimizar suas estratégias de precificação e melhorar a oferta de produtos.

![](foto)

### Objetivos e resultados

O primeiro objetivo é responder às seguintes perguntas sobre o dataset:

- Qual é a quantidade de carros por marca?
- Quais as marcas que possuem a maior média de preço de carros?
- Como o preço se comporta em relação à potência, consumo urbano, comprimento e largura do carro?
- O tipo de carroceria influencia no preço do veículo?

Já a predição dos preços tem por objetivo desenvolver e utilizar um modelo de previsão de preço para estimar o valor de mercado dos carros com base nas suas características. Isso permitirá à empresa ajustar os preços dos veículos de forma mais precisa e competitiva, além de ajudar na avaliação de novos modelos e marcas.

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
- lightgbm

# Análise exploratória de dados 

## Qual é a quantidade de carros por marca?

![](https://github.com/matheussebastiaomendes/ml_lgbmodel/blob/main/imagens/qtd_por_marca_top_10.png)

A marca que lidera com certa vantagem quando comparada à segunda colocada é a Toyota com 32 veículos, seguida da Nissan com 18 e a Mazda com 17. As demais marcas ficaram entre 13 e 9 veículos.

## Quais as marcas que possuem a maior média de preço de carros?

![](https://github.com/matheussebastiaomendes/ml_lgbmodel/blob/main/imagens/media_preco_marca_top_10.png).

O top 3 das marcas que possuem maior média de preço dos veículos são Jaguar, Buick e Porsche, ficando na média de R$ 31.000 a R$ 34.600. Outra marca que possui uma média de valor considerável quando comparada às outras é a BMW, que fica em torno de R$ 26.100. As demais marcas ficam em uma faixa de preço entre R$ 15.000 a R$ 18.000.

## Como o preço se comporta em relação à potência, consumo urbano, comprimento e largura do carro?

![](https://github.com/matheussebastiaomendes/ml_lgbmodel/blob/main/imagens/comportamento.png)

Analisando o gráfico, podemos concluir que o preço diminui conforme um maior consumo urbano e aumenta se potência, largura do carro e comprimento aumentam.

## O tipo de carroceria influencia no preço do veículo?

![](https://github.com/matheussebastiaomendes/ml_lgbmodel/blob/main/imagens/comportamento_carroceria.png)

No dataset, encontramos 5 tipos de carroceria: conversível, hatchback, sedan, wagon (hatchback alongado) e hardtop. Podemos analisar que os carros conversíveis estão em um patamar de preço mais elevado que as carrocerias mais encontradas no dataset, que possuem uma faixa de preços mais acessíveis devido à maior disponibilidade e variação de modelos. A carroceria hardtop possui um intervalo de preço maior.

# Modelo de Predição

## Pré-processamento dos dados
As colunas numéricas e categóricas foram separadas e tratadas. As colunas numéricas receberam um imputer de mediana da coluna analisada nos valores faltantes. Além disso, também foi feito Standard Scaler para a padronização dos dados, para ter média zero e variância unitária. Já nas colunas categóricas, utilizamos o OneHotEncoder para sua transformação.

## Feature selection
Após o tratamento das colunas, utilizamos o SelectKBest para a seleção das features que têm maior impacto no modelo. Para este modelo, selecionamos 10.

## LightGBM
## Métricas
As métricas do modelo 

| Métrica   | Resultado   |
|-----------|-------------|
| RMSE      | 3378.7426   |
| R² Score  | 0.8352      |
| MAE       | 2221.6420   |
| MSE       | 11415901.6063 |
| MAPE      | 0.1566      |

![](https://github.com/matheussebastiaomendes/modelo_predicao/blob/main/imagens/comportamento_modelo_LGBMODEL.png)

As previsões ficam com um erro maior conforme aumentamos o valor dos carros. Testaremos outro modelo para analisar se os valores se adequam melhor à reta.

## Random Forest

Para este modelo, mantivemos o tratamento das colunas numéricas e categóricas e incluímos alguns parâmetros do modelo Random Forest.

As métricas do modelo 

| Métrica   | Resultado   |
|-----------|-------------|
| RMSE      | 2180.4615   |
| R² Score  | 0.9314      |
| MAE       | 1480.7826   |
| MSE       | 4754412.1706 |
| MAPE      | 0.1097      |

![](https://github.com/matheussebastiaomendes/modelo_predicao/blob/main/imagens/comportamento_modelo_RANDOM_FOREST.png)

Neste segundo modelo, podemos ver uma melhora nas métricas com erros menores comparados ao anterior. No gráfico, vemos que os valores da previsão estão muito mais ajustados à reta, ficando bem próximos dos valores reais. Sendo assim, esse é o modelo escolhido para realizar as previsões dos preços dos carros.
