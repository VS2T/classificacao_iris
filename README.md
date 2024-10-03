# classificacao_iris
Linguagem simples de Python para entender a biblioteca pandas e de gerar gráfico.


# Começando a codificação

import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
import seaborn as sns

plt.style.use('ggplot') #Estilo do gráfico

#### Leitura do arquivo Iris em CSV
planta = pd.read_csv("Iris.csv")

#### Exibe as 5 primeiras linhas do DataFrame head(cabeça)
planta.head()

#### Resumo de Informações das colunas
planta.describe()

#### Tipo de dado em cada coluna
planta.dtypes

#### Quantidade total de linhas e colunas
planta.shape

#### Renomenado as volunas
planta.columns = ['id','sepala_comprimento', 'sepala_largura', 'petala_comprimento', 'petala_largura', 'especie']
planta.head()

#### verificando se na coluna sepala_comprimento há algum valor Nulo (NULL)
planta[planta['sepala_comprimento'].isnull()].head() # não tem informação Nula ou NULL

#### Contagem de Valores
planta['especie'].value_counts()

# Visualização dos Dados

#### Criando gráfico com apenas uma linha de código
planta['especie'].value_counts().head(10).plot(kind='bar', figsize=(11, 5), grid=False, rot=0, color ='orange')
#### Kind : Informa o tipo de gráfico escolhido (barras = 'bar')
#### Figsize: Informa o tamanho que o gráfico terá
#### Grid: Permite que apareça as linhas de grade no gráfico.
#### Rot: Informa o grau de toração dos dados que o eixo X devem ter.
#### Color: a cor do gráfico

#### Deixando o gráfico mais agradavel
planta['especie'].value_counts().head(10).plot(kind='bar', figsize=(11, 5), grid=False, rot=0, color ='orange')

plt.title('Conjunto de Dados de Flores da Iris')
plt.xlabel('Classificação') # nomeando o eixo x onde fica o tipo de Iris
plt.ylabel('Quantidade') # nomeando o eixo y onde fica o total de Classificação
plt.show() #Exibindo o gráfico


#Fim da Codificação.
