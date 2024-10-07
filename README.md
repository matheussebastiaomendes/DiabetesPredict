# Diabetes

A diabetes é uma condição crônica que afeta a forma como o corpo metaboliza a glicose, um tipo de açúcar que serve como principal fonte de energia. Existem diferentes tipos de diabetes, sendo os mais comuns o tipo 1 e o tipo 2. No diabetes tipo 1, o corpo não produz insulina, o hormônio responsável por regular os níveis de açúcar no sangue. Já no tipo 2, o corpo não utiliza a insulina de maneira eficaz ou não produz insulina suficiente.

# Modelo Preditivo para diagnóstico de diabetes 

Com base no dataset e nas suas características relevantes, desenvolvemos um modelo de machine learning focado na previsão de pacientes que são positivos para diabetes. Inicialmente, foi realizada uma análise exploratória dos dados para identificar padrões e correlações , o que nos permitiu uma melhor compreensão do conjunto de dados.

Optei por testar mais de um algoritmo de machine learning, como o Random Forest e XGBoost Classifier, para avaliar qual se adequaria melhor à previsão de diagnósticos de diabetes. Após a fase de treino e validação, o modelo foi otimizado através de técnicas como a validação cruzada , maximizando a sua precisão e reduzindo os falsos negativos, que são críticos numa condição como a diabetes.

Com o modelo final, é possível prever com elevada precisão quais pacientes têm maior probabilidade de serem diagnosticados com diabetes, ajudando assim profissionais de saúde a tomar decisões mais informadas e a implementar medidas preventivas com maior antecedência.

Os dados podem ser encontrados no [Kaggle](https://www.kaggle.com/datasets/priyamchoksi/100000-diabetes-clinical-dataset) e foram disponibilizados por [Priyam Choksi](https://www.kaggle.com/priyamchoksi).

![](foto)

### Objetivos e resultados

Responder os seguintes questionamentos:

- Qual é a predominância de diabetes entre os gêneros e qual deles tem maior probabilidade de ter diabetes?
- Há diferença no nivel de glicose no sangue entre gêneros?
- Qual a relação entre as features e o target?


### 🛠️ Ferramentas utilizadas
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## A estrutura do dataset

As colunas do dataset estão organizadas da seguinte forma:

| Coluna                       | Descrição                                                       |
|------------------------------|-----------------------------------------------------------------|
| ano                         | Ano em que os dados foram recolhidos                            |
| genero                       | Género da pessoa (por exemplo, "masculino" ou "feminino").      |                          
| idade          		             | Idade da pessoa (em anos)                                       |
| localizacao                     | Localização geográfica                                          |
| raca:AfricanoAmericano         | Pessoa se identifica como afro-americana (1 = Sim, 0 = Não)     |                          
| raca:Asiatico           	       | Pessoa se identifica como asiática (1 = Sim, 0 = Não)           |
| raca:Caucasiano               | Pessoa se identifica como caucasiana (1 = Sim, 0 = Não)         |
| raca:Hispanico                | Pessoa se identifica como hispânica (1 = Sim, 0 = Não).         |
| raca:Outro                   | Pessoa se identifica como outra raça (1 = Sim, 0 = Não)         |                          
| hipertensao                 | Indica se a pessoa tem hipertensão (1 = Sim, 0 = Não)		       |
| doenca_cardiaca                | Indica se a pessoa tem alguma doença cardíaca(1 = Sim, 0 = Não) |                          
| historico_de_fumante              | Histórico de tabagismo da pessoa                                |
| imc                	         | Índice de Massa Corporal (IMC)                                  |                    
| nivel_hbA1c	                 | Nível de hemoglobina glicada (HbA1c                             |
| nivel_glicose_sanguinea	         | Nível de glicose no sangue no momento da medição                |                          
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

## Qual é a predominância de diabetes entre os gêneros e qual deles tem maior probabilidade de ter diabetes?

![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3odeDiabetes.png)

A quantidade de mulheres presentes no dataset é relativamente maior , entretanto podemos perceber que a quantidade de mulheres que possuem diabetes segue semelhante aos homens, o que gera uma proporção menor de mulheres com diabetes conforme dados da tabela a baixo:

| diabetes| 0 |1|
|-------- |--|--|
|Homem|90.09|9.91|
|Mulher|92.34|7.66|

No dataset homens tem um probabilidade maior de ter diabetes.
  
## Há diferença no nivel de glicose no sangue entre gêneros?

![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20concentra%C3%A7%C3%A3o%20de%20glicose%20no%20sangue.png)

A concentração de glicose no sangue entre os gêneros segue um mesmo padrão, não havendo impacto o gênero.

## Qual a relação entre as features e o target?

### Ano x diabetes
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20ano.png)

Devido à sobreposição significativa entre as classes, podemos esperar que o modelo tenha possiveis dificuldades em distinguir corretamente as classes, olhando para a feature de ano.

### Idade x diabetes
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20idade.png)

Podemos verificar que a distribuição de casos positivos para diabetes segue uma distribuição bimodal, onde há a existência de 2 picos, indicando que existem duas subpopulações distintas dentro dos dados, na casa dos 60 anos e 80. Há um crescente numero de casos a partir dos 40 anos, tendo seu ápice de casos positivos para diabetes perto dos 60 anos de idade. Há um comportamento interessante entre as classes em relação ao target, sugerindo que as diferenças nas distribuições das features contribuem para uma separação mais clara entre as mesmas.

### Imc x diabetes
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20imc.png)

O imc apresenta um comportamento parecido nas duas classes, positiva e negativa, ambos tem um pico na casa dos 30.

### hbA1c x diabetes
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20nivel_hbA1c.png)

Pessoas que tem diabetes apresentam nivel de HBA1C maiores que 5, tendo uma alta concentração de pessoas com niveis proximos de 6 e 9. Há uma separação interessante entre as classes, o que pode ajudar no desempenho do modelo.

### Nivel de glicose no sangue x diabetes
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Distribui%C3%A7%C3%A3o%20de%20nivel_glicose_sanguinea.png)

A prensença de diabetes está com maior concentração em niveis de glicose sanguinea proxima a 150, podemos observar que há uma diferença no comportamento entre as duas classes, com boas separações e diferentes picos entre classes.

# Modelo de Predição

### Pré-processamento dos dados
As colunas numéricas e categóricas foram separadas e tratadas. As colunas numéricas receberam um imputer de mediana da coluna analisada nos valores faltantes. Além disso, também foi feito Standard Scaler para a padronização dos dados, para ter média zero e variância unitária. Já nas colunas categóricas, utilizamos o OneHotEncoder para sua transformação.

### Balanceamento de classes

Verificamos que a classe minoritária (1 - tem diabetes)  possui uma representatividade de 8.60 % e a classe majoritária (0 - não tem diabetes) 91.40 %, esse desbalanceamento pode influenciar no desempenho do modelo, para tratar esse desbalanceamento optei por utilizar um Class Weight

Calculando chegamos no seguinte peso para cada uma das classes:

| Classe    | Peso         |
|-----------|-------------|
| 0  | 0.5480853551593101 |
| 1  |5.699088145896656   |


### Feature selection
Após o tratamento das colunas, utilizamos o RFE para a seleção das features que têm maior impacto no modelo. O Recursive Feature Elimination roda o modelo inicialmente com todas as características disponíveis, avaliando sua importância e removendo aquelas que possuem uma menor significância no nosso modelo, até chegar no número escolhido de features para o treinamento, no nosso caso, são 10.

## Random Forest Classifier


### Métricas
As métricas do modelo 


| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |   0.9608    |
| Precison  |   0.8482    |
| Recall    |   0.7013    |
| f1-score  |   0.7678    |
| Roc Auc   |   0.9606    |

### Métricas apuradas após a validação cruzada

A validação cruzada divide o dataset em varias partições os chamados folds, separa partes diferentes dos dados em cada fold para treinamento e validação, a partir dai extraimos as métricas de avaliação de cada treinamento realizado e fazemos uma média dos resultados, nos trazendo uma visão mais realista do real desempenho do modelo.

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |   0.9660    |
| Precison  |   0.8714    |
| Recall    |   0.7105    |
| f1-score  |   0.7822    |
| Roc Auc   |   0.9717    |

### Matriz de confusão
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Matriz%20de%20confusao%20Random%20Forest.png)

### Curva Roc

![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Roc%20Random%20Forest.png)

## Xgboost Classifier

Para este modelo, mantivemos o tratamento das colunas numéricas e categóricas e incluímos alguns parâmetros do modelo Xgboost Classifier.

As métricas do modelo 

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |   0.9628    |
| Precison  |   0.8791    |
| Recall    |   0.6926    |
| f1-score  |   0.7748    |
| Roc Auc   |   0.9596    |


### Métricas apuradas após a validação cruzada

| Métrica   | Resultado   |
|-----------|-------------|
| Accuracy  |   0.9679    |
| Precison  |   0.8934    |
| Recall    |   0.7116    |
| f1-score  |   0.7921    |
| Roc Auc   |   0.9725    |

### Matriz de confusão
![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/Matriz%20de%20Confus%C3%A3o%20Xgboost.png)

### Curva Roc

![](https://github.com/matheussebastiaomendes/DiabetesPredict/blob/main/imagens/ROC%20Xgboost.png)

# Considerações finais


