# breast_cancer_diagnostic

Este é um projeto de Ciência de Dados que tem como objetivo desenvolver um modelo de máquina preditiva para prever, com base nas características das variáveis, se o câncer é benigno ou maligno. A capacidade de identificar com precisão o tipo de câncer com base em dados clinicamente relevantes é de extrema importância na área da saúde, uma vez que orienta decisões de tratamento e cuidados médicos.

Foi adotado o framework CRISP-DM (Cross-Industry Standard Process for Data Mining), amplamente reconhecido e utilizado na área de Ciência de Dados devido à sua estrutura organizada e abordagem sistemática. O CRISP-DM nos proporciona um roteiro claro e flexível para lidar com problemas complexos de análise de dados, garantindo que abordemos cada etapa do processo com rigor e compreensão.

**BUSINESS UNDERSTANDING**

O objetivo primordial deste projeto de Ciência de Dados é desenvolver um modelo de máquina preditiva para a classificação de casos de câncer de mama como benignos ou malignos

O diagnóstico preciso de câncer de mama é fundamental para garantir tratamentos adequados e oportunos, aumentando as chances de recuperação e sobrevivência dos pacientes.

O modelo previsto deve ser capaz de avaliar pacientes com base nas características calculadas a partir de uma imagem digitalizada de um aspirado com agulha fina (PAAF) de uma massa mamária. Eles descrevem características dos núcleos celulares presentes na imagem.

O espaço tridimensional é aquele descrito em: [KP Bennett e OL Mangasarian: "Robust Linear Programming Discrimination of Two Linearly Inseparable Sets", Optimization Methods and Software 1, 1992, 23-34].

**DATA UNDERSTANDING**

Fonte de dados:

Dataset está disponível através do servidor FTP UW CS ftp

ftp.cs.wisc.edu cd math-prog/cpo-dataset/machine-learn/WDBC/

Também pode ser encontrado no UCI Machine Learning Repository:

https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsi+%28Diagnostic%29

No Kaggle:

https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data

**DATA PREPARATION**

Preparação dos Dados para gerar a ABT (Tabela Analítica de Modelagem)

Remoção de variáveis para o tratamento dos dados
Geração dos metadados
Tratamento de valores nulos
Tratamento de categóricas de alta cardinalidade (LabelEncoder)
Tratamento de categóricas de baixa cardinalidade (OneHotEncoder)

**MODELING**

**Feature Selection**
O processo de Feature Selection é uma etapa fundamental na preparação e modelagem de dados em ciência de dados e aprendizado de máquina. Consiste em selecionar um subconjunto das características (features) mais relevantes e informativas dos dados para construir modelos preditivos mais eficazes.

Nesse contexto, foram geradas duas versões da nossa tabela de dados (ABT):

Aplicação do algoritmo GradientBoostingClassifier para calcular a importância de cada feature no processo de classificação.
Técnica de Análise de Componentes Principais (PCA) para redução de dimensionalidade
Feature Importance
Foi realizado testes com três algoritmos de seleção de features:

GradientBoostingClassifier
DecisionTreeClassifier
RandomForestClassifier
O objetivo desses testes foi identificar as features mais relevantes em nosso conjunto de dados.

Após a análise comparativa dos três algoritmos de seleção de features, o GradientBoostingClassifier demonstrou um desempenho superior na identificação das features mais relevantes para a tarefa de classificação.

**Train Model**
Nesta fase da análise de desempenho, utilizamos três algoritmos de classificação amplamente reconhecidos:

Logistic Regression
Decision Tree Classifier
Random Forest Classifier.
O objetivo inicial foi avaliar o desempenho desses algoritmos em nosso conjunto de dados, com foco especial nas métricas:

Recall
Precision
O recall é uma métrica crítica em problemas em que a detecção de casos positivos é de grande importância em diagnóstico médico. Mede a capacidade do modelo em identificar corretamente todos os casos positivos, minimizando falsos negativos.


**EVALUATION**

Foram realizados treinamentos com três modelos de Machine Learning:

Random Forest
Logistic Regression
Decision Tree Classifier
No entanto, o destaque dessa etapa reside na seleção de features, onde empregamos duas abordagens distintas para otimizar o desempenho dos modelos.

A primeira abordagem envolve a seleção de features por meio do GradientBoostingClassifier, que é uma técnica de Feature Importance.
A segunda abordagem utiliza a técnica de Análise de Componentes Principais (PCA), que é uma técnica de redução de dimensionalidade.
Nossa meta principal nesta etapa era realizar um comparativo abrangente entre duas abordagens de seleção de features: Feature Importance com GradientBoostingClassifier e Análise de Componentes Principais (PCA).

No entanto, é importante observar que, apesar da nossa análise, os resultados não revelaram diferenças expressivas no desempenho dos modelos.

O modelo LogisticRegression com feature selection por gradient boosting destacou-se ao apresentar o melhor desempenho, especialmente considerando as métricas: recall e precision.

