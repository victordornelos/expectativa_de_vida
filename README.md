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
1. [Descrição](https://github.com/victordornelos/regressao_python#1-descrição)
2. [Objetivo](https://github.com/victordornelos/regressao_python#2-objetivo)
3. [Regressão Linear com Dados em Painel](https://github.com/victordornelos/regressao_python#3-regressão-linear)
4. [Metodologia](https://github.com/victordornelos/regressao_python#4-metodologia)
5. [Resultados](https://github.com/victordornelos/regressao_python#5-resultados)
6. [Referências](https://github.com/victordornelos/regressao_python#6-referências)

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

