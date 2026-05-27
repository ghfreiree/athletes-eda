# Athletes EDA

Este projeto realiza uma Análise Exploratória de Dados (EDA) em uma base de dados contendo métricas de treino, atributos físicos e indicadores de saúde de 973 membros de academia. O foco central da investigação é identificar quais características demográficas, fisiológicas e hábitos de treino possuem maior associação estatística com a redução do **Percentual de Gordura Corporal (`Fat_Percentage`)**.

O notebook foi estruturado seguindo as melhores práticas, dividindo a análise em fases lógicas: Mapeamento Estatístico (Heatmap), Análise Univariada (Estudo de Distribuições) e Análise Bivariada Focada com investigação de Causalidade Biológica e Fatores de Gênero.

---

## Objetivo do Projeto
Identificar, quantificar e justificar criticamente quais características e hábitos dos atletas de academia possuem maior associação com um menor percentual de gordura (BF), isolando correlações estatísticas superficiais de fatores causais biológicos reais.

---

## Sobre o Dataset
A análise foi construída em cima do dataset `gym_members_exercise_tracking.csv` encontrado no Kaggle. [Esse conjunto de dados](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset) oferece uma visão das rotinas de exercícios, atributos físicos e métricas de condicionamento físico de membros de academia.

---

## Dicionário de Variáveis
* **Idade (`Age`):** Idade do membro da academia.
* **Gênero (`Gender`):** Gênero do membro da academia (Masculino ou Feminino).
* **Peso (`Weight (kg)`):** Peso do membro em quilogramas.
* **Altura (`Height (m)`):** Altura do membro em metros.
* **BPM Máximo (`Max_BPM`):** Frequência cardíaca máxima (batimentos por minuto) durante as sessões de treino.
* **BPM Médio (`Avg_BPM`):** Frequência cardíaca média durante as sessões de treino.
* **BPM em Repouso (`Resting_BPM`):** Frequência cardíaca em repouso antes do treino.
* **Duração da Sessão (`Session_Duration (hours)`):** Duração de cada sessão de treino em horas.
* **Calorias Queimadas (`Calories_Burned`):** Total de calorias queimadas durante cada sessão.
* **Tipo de Treino (`Workout_Type`):** Tipo de treino realizado (Cardio, Strength, Yoga, HIIT).
* **Percentual de Gordura (`Fat_Percentage`):** Percentual de gordura corporal do membro (Variável Alvo).
* **Consumo de Água (`Water_Intake (liters)`):** Consumo diário de água durante os treinos (em litros).
* **Frequência de Treino (`Workout_Frequency (days/week)`):** Número de sessões de treino por semana.
* **Nível de Experiência (`Experience_Level`):** Nível de experiência no treino, variando de iniciante (1) a especialista (3).
* **IMC (`BMI`):** Índice de Massa Corporal, calculado a partir da altura e do peso.

---

## Estrutura da Análise no Notebook

### 1. Configuração do Ambiente e Bibliotecas
Importação de pacotes analíticos essenciais (`pandas`, `matplotlib`, `seaborn`, `math`) e carregamento da base de dados.

### 2. Mapeamento Inicial (Matriz de Correlação)
Construção de um Heatmap de correlação linear para triagem inicial das variáveis preditivas em relação à variável alvo (`Fat_Percentage`). Esta etapa serve como bússola para selecionar quais variáveis merecem investigação profunda na fase bivariada.

### 3. Análise Univariada
Implementação de loops otimizados e grades de subplots (`plt.subplots`) para analisar o perfil isolado da população:
* **Variáveis Categóricas:** Frequência e contagem volumétrica (`sns.countplot`).
* **Variáveis Numéricas:** Curvas de densidade e assimetria de distribuições (`sns.histplot` com KDE).

### 4. Análise Bivariada
Cruzamento direcionado das variáveis comportamentais contra o BF para validar as hipóteses do Heatmap, seguido por um estudo de interdependência de variáveis (ex: cruzando Experiência com Gasto Calórico) para mapear o ecossistema causal por trás da performance dos atletas.

### 5. Análise de Médias e Fatores Biológicos
Segmentação das médias reais de BF agrupadas por variáveis estruturais, quantificando o impacto percentual exato do Gênero e do Nível de Experiência na composição corporal.

---

## Principais Descobertas e Insights

1. **O Bloco de Hábitos e Consistência (Correlações Fortes):**
   * O nível de experiência (`Experience_Level`) lidera a associação inversa com o BF (**-0.65**). Atletas experientes registram, em média, uma redução marcante de **12.5% de BF** em comparação com indivíduos intermediários/iniciantes.
   * Três variáveis comportamentais apresentam uma força de associação quase idêntica: o gasto calórico (`Calories_Burned`: **-0.60**), a ingestão de água (`Water_Intake`: **-0.59**) e a duração da sessão (`Session_Duration`: **-0.58**), seguidos pela frequência semanal (**-0.54**).
   * *A Causalidade Real:* A análise provou que a experiência ou o consumo de água não reduzem a gordura por si sós, mas funcionam como variáveis *proxy* de um estilo de vida modificado. Atletas experientes sustentam treinos mais longos, gerando um gasto calórico superior e demandando maior hidratação. O déficit calórico acumulado é o verdadeiro motor biológico da queima de gordura.

2. **O Fator Gênero (`Gender`):**
   * A análise de médias revelou uma separação fisiológica clara na base: o público masculino apresenta, em média, **5.1% a menos de BF** do que o público feminino, refletindo linhas de base hormonais e metabólicas naturais de cada gênero, mesmo sob rotinas de treino equivalentes.

3. **Mitos Desmistificados (Correlação Nula):**
   * As variáveis de batimentos cardíacos (`Avg_BPM` e `Max_BPM` a **-0.01**) e a `Age` (**0.00**) possuem correlação linear **nula** com o percentual de gordura. O estresse cardíaco momentâneo dita apenas o cansaço do exercício na hora, enquanto a composição corporal responde ao volume e consistência acumulados a longo prazo.

---

## Tecnologias Utilizadas
* **Python 3.x**
* **Pandas:** Manipulação de dados e cálculo de matrizes estatísticas.
* **Matplotlib & Seaborn:** Criação de visualizações avançadas, mapas de calor, boxplots e subplots automatizados.
* **Jupyter Notebook / Google Colab:** Ambiente de desenvolvimento interativo.
