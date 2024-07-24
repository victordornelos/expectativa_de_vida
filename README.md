# Análise dos fatores que influenciam a expectativa de vida média dos países 
![Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)
![Python](https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

<p align="center">
  <img src="imagem/foto.png" alt="Saúde">
</p>

**Autor:** Victor Flávio P. Dornelos\
**E-mail:** victor.dornelos@hotmail.com\
**Linkedin:** [Victor Flávio Pereira Dornelos](https://www.linkedin.com/in/victor-flavio-pereira-dornelos/)

## Sumário
1. [Descrição](https://github.com/victordornelos/expectativa_de_vida#1-descrição)
2. [Objetivo](https://github.com/victordornelos/expectativa_de_vida#2-objetivo)
3. [Regressão Linear com Dados em Painel](https://github.com/victordornelos/expectativa_de_vida#3-regressão-linear-com-dados-em-painel)
4. [Metodologia](https://github.com/victordornelos/expectativa_de_vida#4-metodologia)
5. [Resultados](https://github.com/victordornelos/expectativa_de_vida#5-resultados)
6. [Referências](https://github.com/victordornelos/expectativa_de_vida#6-referências)

## 1. Descrição:
O estudo da expectativa de vida tem um destaque significativo nas ciências sociais, com a Economia desempenhando um papel crucial ao promover políticas públicas que visam aumentar não apenas a longevidade, mas também a qualidade de vida. Nesse contexto, a econometria emerge como uma ferramenta essencial, utilizando estatística e matemática aplicada para conduzir pesquisas econômicas. Ela trabalha com dados sociais, possibilitando a realização de inferências causais e previsões que auxiliam os formuladores de políticas em suas decisões.

Um método econométrico particularmente útil para entender os fatores que mais impactam a expectativa de vida média nos países é a regressão em dados em painel. Esse método permite uma inferência causal a partir de dados que variam em duas dimensões: entre indivíduos e ao longo do tempo. Suas vantagens incluem a mitigação da heterocedasticidade e colinearidade, além de proporcionar maior informação e variabilidade, tornando o estudo mais robusto. Adicionalmente, ferramentas auxiliares como efeitos fixos e erros robustos são úteis para aumentar a eficiência do modelo.

## 2. Objetivo:
O objetivo desta pesquisa é explorar dados socioeconômicos relacionados à expectativa de vida média dos países, permitindo estabelecer relações causais. Para isso, serão utilizados métodos econométricos aplicados a dados em painel, detalhando seu funcionamento e aplicação prática por meio da linguagem Python, além de apresentar os resultados obtidos. Adicionalmente, serão abordadas ferramentas auxiliares, como efeitos fixos e erro padrão robusto, explicando seus conceitos e aplicações para aprimorar a robustez e eficiência dos modelos econométricos utilizados.

## 3. Regressão linear com dados em painel:
A regressão linear com dados em painel utiliza duas dimensões para cada variável visando estimar o valor de uma variável dependente y com base em uma variável independente x e outras variáveis de controle. Este método é uma forma de inferência causal que cria uma reta com coeficientes que minimizam os resíduos quadráticos por meio do método dos Mínimos Quadrados Ordinários (OLS). Os coeficientes são testados por meio de testes de hipótese para determinar sua significância estatística, frequentemente utilizando o conceito de p-valor para verificar a probabilidade de aceitar ou rejeitar a hipótese nula dentro de um nível de confiança especificado.

Para a aplicação do OLS, é necessário respeitar uma série de pressupostos. Caso contrário, a robustez dos resultados pode ser comprometida. As principais características desses pressupostos são:
Amostragem ampla e aleatória dos dados.

- Distribuição normal dos resíduos.
- Inexistência de autocorrelação, ou seja, os resíduos não devem depender de observações passadas.
- Homoscedasticidade, ou seja, variância constante dos resíduos ao longo da série.
- Não correlação entre as variáveis independentes e os resíduos.
- Resíduos distribuídos de forma aleatória, sem padrões discerníveis.

É comum que alguns desses pressupostos sejam violados inicialmente devido à natureza complexa dos dados em ciências sociais. Diversas ferramentas podem ser utilizadas para mitigar esses problemas, como a transformação dos dados usando logaritmos ou diferenciação, a inclusão de variáveis de controle, a utilização de erros padrão robustos e, no caso deste estudo, o uso de dados em painel. Os dados em painel permitem estimar valores utilizando observações de múltiplos indivíduos ao longo do tempo, diferente da regressão comum que é limitada a um ponto no tempo ou a um único indivíduo, resultando em estimativas menos precisas.

A expressão genérica do modelo de regressão com dados em painel é:

<p align="center">
  <img src="https://latex.codecogs.com/svg.latex?\color{white}Y_i_t=\beta_i+\beta_1X_i_t+\epsilon_i_t">
</p>

Onde:
- Yit é a variável dependente para o indivíduo ii no tempo tt.
- βi é o coeficiente de intercepto, representando o valor de Y para cada indivíduo independentemente de X.
- β1 é o coeficiente angular, indicando o impacto de uma variação unitária em X sobre Y.
- Xit é a variável independente para o indivíduo i no tempo t.
- ϵit são os resíduos do modelo.

Nos modelos com dados em painel, é comum a utilização de efeitos fixos para reduzir a heterocedasticidade e a colinearidade. Este método assume que existem características não observáveis constantes ao longo do tempo que variam entre os indivíduos, controlando os vieses que poderiam comprometer a confiabilidade do modelo. Assim, a variação entre os indivíduos não ganha importância, restando a variação dentro da entidade.

Devido à natureza dos efeitos fixos, que trabalham com várias observações da mesma entidade, economistas defendem que a possibilidade de colinearidade é alta, sendo necessário utilizar erros padrão robustos agrupados. Dessa forma, ao utilizar esses erros padrão agrupados, a correlação entre os indivíduos é levada em conta durante o cálculo dos coeficientes da equação.

## 4. Metodologia

A metodologia deste estudo foi baseada no livro "The Effect: An Introduction to Research Design and Causality" de Nick Huntington-Klein. Inicialmente, os dados foram obtidos a partir de um dataset disponibilizado no Kaggle, que utiliza informações fornecidas pelo Banco Mundial. O dataset está disponível nos arquivos do projeto e o link será incluído nas referências. A linguagem de programação escolhida foi Python, utilizando Jupyter Notebook integrado ao Visual Studio Code (VSC) e PyCharm Professional

Primeiramente, foi realizada uma análise exploratória inicial dos dados categóricos usando a biblioteca Pandas, criando um DataFrame específico para esses dados. Em seguida, um gráfico foi criado usando Plotly para analisar os grupos de renda, além de um dashboard com um mapa que mostra a evolução da expectativa de vida nos países ao longo do tempo.

1- Tratando os dados:
```python
# Bibliotecas
import pandas as pd
import plotly.express as px

# Importando dados
data = pd.read_csv('expectativa_vida.csv')

# Tratando
df = pd.DataFrame()
df['Países'] = data['Country Name']
df['Anos'] = data['Year']
df['Cod país'] = data['Country Code']
df['Expectativa de vida'] = data['Life Expectancy World Bank']
df['Região'] = data['Region']
df['Grupo de renda'] = data['IncomeGroup']

# Salvando
df.to_csv('mapa.csv', index=False)
```
2- Gráfico da média:

```python
mean_life_expectancy_per_year = df.groupby('Anos')['Expectativa de vida'].mean().reset_index()

#Gráfico
plt.figure(figsize=(12, 6))
sns.lineplot(data=mean_life_expectancy_per_year, x='Anos', y='Expectativa de vida')
plt.title('Expectativa de Vida Média Mundial')
plt.xlabel('Ano')
plt.ylabel('Expectativa de Vida Média')
plt.xticks(mean_life_expectancy_per_year['Anos']) 
plt.grid(True)
plt.grid(False)
plt.show()
```
3- Gráfico de grupo de renda:
```python
# Agrupando os dados por ano e grupo de renda para obter a média da expectativa de vida
grouped_data = data.groupby(['Anos', 'Grupo de renda'])['Expectativa de vida'].mean().reset_index()

# Dashboard
fig = px.bar(grouped_data, 
             x='Grupo de renda', 
             y='Expectativa de vida', 
             animation_frame='Anos', 
             animation_group='Grupo de renda', 
             range_y=[0, 100], 
             title='Expectativa de Vida Média por Grupo de Renda ao Longo dos Anos',
             labels={'Expectativa de vida': 'Expectativa de Vida Média', 'Grupo de renda': 'Grupo de Renda'},
             color='Grupo de renda',
             color_discrete_sequence=px.colors.qualitative.Vivid)

fig.update_layout(yaxis=dict(title='Expectativa de Vida Média'),
                  xaxis=dict(title='Grupo de Renda'),
                  title={'text': 'Expectativa de Vida Média por Grupo de Renda ao Longo dos Anos', 'x': 0.5},
                  uniformtext_minsize=8, uniformtext_mode='hide')

fig.update_traces(texttemplate='%{y:.2f}', textposition='outside', textfont=dict(color='white'))

fig.show()
```
4- Dashboard do mapa:
```python

#Tratando os dados para compatibilidade 
average_life_expectancy_by_country_year = data.groupby(['Anos', 'Países'])['Expectativa de vida'].mean().reset_index()
average_life_expectancy_by_country_year = average_life_expectancy_by_country_year.rename(columns={'Anos': 'Year', 'Países': 'Country', 'Expectativa de vida': 'Life Expectancy'})

# Dashboard 
fig = px.choropleth(
    average_life_expectancy_by_country_year,
    locations='Country',
    locationmode='country names',
    color='Life Expectancy',
    color_continuous_scale=px.colors.sequential.Viridis,  
    title='Expectativa de Vida Média por País',
    labels={'Life Expectancy': 'Expectativa de Vida'},
    animation_frame='Year',  
    width=1200,  
    height=800   
)

fig.update_layout(
    title={
        'text': 'Dashboard da Expectativa de Vida por País',
        'y': 0.9,
        'x': 0.5,
        'xanchor': 'center',
        'yanchor': 'top'
    },
    geo=dict(
        showcoastlines=True,
        coastlinecolor="Black",
        showland=True,
        landcolor="white"
    )
)

fig.show()
```
Após essa análise preliminar, foram selecionadas as principais variáveis para modelar a regressão linear com dados em painel, utilizando a biblioteca Statsmodels. O modelo foi implementado com o uso de efeitos fixos e erros padrão robustos agrupados. Por fim, foi criado um gráfico de dispersão utilizando a biblioteca Seaborn para analisar se os pressupostos do OLS foram atendidos, verificando assim a robustez do modelo.

5- Tratando dados para o modelo:
```python
# Bibliotecas
import pandas as pd
import statsmodels.formula.api as smf
import seaborn as sns
import matplotlib.pyplot as plt

# Importando dados
data = pd.read_csv('expectativa_vida.csv')

# Tratando o database
data.set_index(['Country Name', 'Year'], inplace=True)
variables = data.drop(columns=['Country Code', 'Region', 'Corruption','Injuries', 'Communicable', 'NonCommunicable'])
variables = variables.dropna()
df = variables.reset_index()
```
6- Modelando:
```python
# Modelando 
formula = 'Q("Life Expectancy World Bank") ~ Q("Prevelance of Undernourishment") + Q("CO2") + Q("Health Expenditure %") + Q("Education Expenditure %") + Q("Unemployment") + Q("Sanitation") + C(Q("Country Name")) + C(Q("IncomeGroup"))'
fixed_effects_model = smf.ols(formula, data=df).fit(cov_type='cluster', cov_kwds={'groups': df['Country Name']})
fixed_effects_model.summary()
```
7- Análise dos resíduos:
```python
# Calculando os valores previstos
df['predicted'] = fixed_effects_model.fittedvalues
# Calculando os resíduos
df['residuals'] = fixed_effects_model.resid

# Gráfico de dispersão 
plt.figure(figsize=(10, 6))
sns.scatterplot(x='predicted', y='residuals', data=df)
plt.axhline(y=0, color='red', linestyle='-') 
plt.title('Gráfico de Dispersão dos Resíduos')
plt.xlabel('Valores Previstos')
plt.ylabel('Resíduos')
plt.grid(False)
plt.show()
```
Esta abordagem permitiu uma análise detalhada e robusta dos dados, contribuindo para uma melhor compreensão das relações causais presentes no conjunto de dados estudado.

## 5. Resultados:
A ideia central deste estudo é verificar a hipótese de que fatores socioeconômicos impactam a expectativa de vida média dos países. A partir dessa premissa, buscamos concluir se ações, como políticas públicas, são capazes de melhorar a longevidade dos cidadãos. Além disso, é interessante observar se houve mudanças significativas ao longo dos anos, tanto na média da expectativa de vida quanto em seu perfil.

<p align="center">
  <img src="imagem/gráfico1.png" alt="Saúde">
</p>

Analisando o gráfico acima, percebe-se que as pessoas estão vivendo cada vez mais ao longo dos anos, com um crescimento linear de 2001 até 2019. Isso torna ainda mais relevante compreender os fatores que contribuíram para essa melhoria. Além disso, é crucial verificar se essa tendência ocorreu em todos os países, independentemente da renda. No gráfico abaixo, é possível identificar dois comportamentos: quanto mais pobre o grupo, menor sua expectativa de vida; e quanto mais pobre foi o grupo de renda, maior foi o crescimento da expectativa de vida durante o período analisado.

<p align="center">
  <img src="imagem/life_expectancy_by_income_group.gif" alt="Saúde">
</p>

O mapa abaixo reforça essa análise, indicando que as regiões mais pobres tiveram os maiores aumentos na duração da vida em comparação com as mais ricas. No entanto, é importante notar que nem todos os países tiveram dados disponíveis para esta pesquisa.

<p align="center">
  <img src="imagem/life_expectancy_dashboard.gif" alt="Saúde">
</p>

O modelo econométrico utilizado é representado pela equação abaixo, empregando variáveis socioeconômicas para alcançar a maior eficiência possível:

<p align="center">
  <img src="https://latex.codecogs.com/svg.latex?\color{white}\text{Life\_Expectancy}_{it}=\alpha+\beta_1\text{Prevalence\_of\_Undernourishment}_{it}+\beta_2\text{CO2}_{it}+\beta_3\text{Health\_Expenditure\_\%}_{it}+\beta_4\text{Education\_Expenditure\_\%}_{it}+\beta_5\text{Unemployment}_{it}+\beta_6\text{Sanitation}_{it}+\sum_{j=1}^{n-1}\gamma_j\text{Country\_Name}_j+\sum_{k=1}^{m-1}\delta_k\text{Income\_Group}_k+\epsilon_{it}">
</p>

Onde:

1. **Life Expectancy<sub>it</sub>** - Expectativa de vida no país *i* no tempo *t*.
2. **α** - Intercepto do modelo.
3. **β<sub>1</sub> Prevalence of Undernourishment<sub>it</sub>** - Coeficiente e variável para a prevalência de subnutrição no país *i* no tempo *t*.
4. **β<sub>2</sub> CO2<sub>it</sub>** - Coeficiente e variável para a emissão de CO2 no país *i* no tempo *t*.
5. **β<sub>3</sub> Health Expenditure %<sub>it</sub>** - Coeficiente e variável para o percentual de gastos com saúde no país *i* no tempo *t*.
6. **β<sub>4</sub> Education Expenditure %<sub>it</sub>** - Coeficiente e variável para o percentual de gastos com educação no país *i* no tempo *t*.
7. **β<sub>5</sub> Unemployment<sub>it</sub>** - Coeficiente e variável para a taxa de desemprego no país *i* no tempo *t*.
8. **β<sub>6</sub> Sanitation<sub>it</sub>** - Coeficiente e variável para a cobertura de saneamento básico no país *i* no tempo *t*.
9. **∑<sub>j=1</sub><sup>n-1</sup> γ<sub>j</sub> Country Name<sub>j</sub>** - Termo que representa os dummies para os diferentes países, com γ<sub>j</sub> sendo o coeficiente para o país *j*.
10. **∑<sub>k=1</sub><sup>m-1</sup> δ<sub>k</sub> Income Group<sub>k</sub>** - Termo que representa os dummies para os diferentes grupos de renda, com δ<sub>k</sub> sendo o coeficiente para o grupo de renda *k*.
11. **ϵ<sub>it</sub>** - Termo de erro no país *i* no tempo *t*.

Os resultados obtidos foram bastante satisfatórios. O F-valor demonstrou significância estatística, e o R² de 97,4% indicou que o modelo captura de forma robusta a variação da variável dependente. Em relação ao teste de hipóteses, duas variáveis importantes apresentaram significância acima do nível de confiança desejado (10%): classe média-baixa e investimento em educação, ambas passaram no teste t-valor. Quanto à autocorrelação, o valor DW de 1.491 foi classificado como inclusivo, e os resíduos apresentaram uma distribuição normal.

### Principais insights:

- Quanto mais rico for o país, maior será a duração da vida. 
- Desnutrição tem impacto negativo de 18%. 
- A poluição representada por emissão de CO2 teve um baixo impacto negativo, possivelmente porque os países que mais emitem são os mais ricos. 
- Investimento em saúde tem um forte impacto positivo na expectativa de vida. 
- O desemprego impacta negativamente com 8%, novamente demonstrando a importância dos fatores econômicos. 
- Nível de saneamento tem impacto positivo de 15%.

Realizando um gráfico de dispersão dos resíduos para verificação dos pressupostos, foi observado que há heterocedasticidade, mesmo com todas as tentativas de ajuste, o que pode impactar a confiabilidade dos resultados.

<p align="center">
  <img src="imagem/Gráfico 2.png" alt="Saúde">
</p>

Este estudo destaca a importância de fatores socioeconômicos na expectativa de vida dos países, sugerindo que políticas públicas eficazes podem melhorar significativamente a longevidade dos cidadãos. Apesar de algumas limitações, como a heterocedasticidade observada, os insights obtidos fornecem uma base sólida para futuras pesquisas e intervenções.

# 6. Referências:
HUNTINGTON-KLEIN, Nick. The Effect: An Introduction to Research Design and Causality. Boca Raton, FL: CRC Press, 2022.

CHAVAN, Shritej Shrikant. Life Expectancy and Socio Economic (World Bank) [Base de dados]. Disponível em: https://www.kaggle.com/datasets/mjshri23/life-expectancy-and-socio-economic-world-bank. Acesso em: 24 jul. 2024.

