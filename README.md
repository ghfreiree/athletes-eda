# Análise de Dados: Fatores de Redução de BF em Atletas de Academia

## Visão Geral
Este projeto de **Análise Exploratória de Dados (EDA)** tem como objetivo investigar e descobrir quais são os principais fatores que contribuem para a diminuição do percentual de gordura (BF - *Body Fat*) em frequentadores de academia.

Através da manipulação de dados e criação de visualizações, o projeto extrai *insights* práticos sobre como variáveis como a frequência semanal de treinos e o nível de experiência do atleta impactam diretamente os resultados físicos.

## Sobre o Conjunto de Dados
A análise foi construída em cima do dataset `gym_members_exercise_tracking.csv` encontrado no Kaggle, que contém registros sobre a rotina de exercícios, nível de experiência, métricas corporais e outras informações relevantes dos atletas. 

[![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=Kaggle)](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset)



## Algumas visualizações

<p align="center">
  <img src="images/download (25).png" alt="Gráfico Dispersão de BF por Modalidade" width="500">
  <img src="images/download (22).png" alt="Gráfico Relação Duração do Treino vs BF" width="500">
  <img src="images/download (23).png" alt="Gráfico Média de BF por Frequência de Treino" width="500">
</p>

## Principais Insights
Durante a exploração dos dados, padrões muito claros de progressão foram identificados:
* **Mais Experiência -> Mais Resultados:** Foi observada uma diferença de **12,5% na média de BF** entre indivíduos de nível intermediário e experiente.
* **O Peso da Constância:** Os dados revelaram que a diferença de percentual de gordura entre um atleta intermediário e um experiente é estatisticamente muito semelhante à diferença entre pessoas que treinam **3 vezes na semana versus 5 vezes na semana**. 

## Tecnologias e Bibliotecas Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** Pandas
* **Visualização de Dados:** Matplotlib, Seaborn
* **Ambiente de Desenvolvimento:** Jupyter Notebook / Google Colab

## Como Executar o Projeto

-  Clone este repositório para a sua máquina local:
  
   ```bash
   git clone https://github.com/ghfreiree/fitness-data-insights.git
   
  ---
*Desenvolvido com dedicação para aprofundamento em Data Science*
