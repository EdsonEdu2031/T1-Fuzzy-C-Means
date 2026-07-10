## Resumo
Este projeto implementa manualmente o algoritmo de agrupamento Fuzzy C-Means sobre a base de dados Iris, explorando todas as etapas do algoritmo, desde a inicialização da matriz de pertinência até a atualização iterativa dos centroides e dos graus de pertencimento das amostras. Diferentes valores para o coeficiente de fuzzificação (m) foram avaliados utilizando o coeficiente de Silhouette e um score ponderado que considera a proporção de ruídos, permitindo selecionar automaticamente a configuração com melhor desempenho.

Além da aplicação sobre a base Iris completa, também foi realizada uma análise considerando apenas as espécies Virginica e Versicolor, possibilitando comparar o comportamento do algoritmo em diferentes cenários.

O projeto foi desenvolvido como atividade da disciplina de Aprendizado Não Supervisionado, no 5º semestre do curso de Ciência de Dados e Inteligência Artificial.


## Tecnologias utilizadas
- Python;
- Pandas e NumPy para manipulação dos dados;
- Scikit-learn (MinMaxScaler e Silhouette Score);
- Matplotlib e Seaborn para visualização.

## Como executar
1. Clone o repositório;
2. Instale as dependências;
3. Execute célula por célula o main.ipynb.

## Funcionalidades
- Implementação manual do algoritmo Fuzzy C-Means, sem utilização de bibliotecas especializadas;
- Inicialização aleatória da matriz de pertinência (W);
- Atualização iterativa dos centroides e dos graus de pertinência;
- Classificação das amostras com base em um limiar (threshold);
- Avaliação automática dos agrupamentos utilizando o coeficiente de Silhouette;
- Seleção do melhor coeficiente de fuzzificação (*m*) por meio de um score ponderado;
- Visualização dos agrupamentos utilizando pairplots com os centroides destacados.

## Resultados

A implementação manual do algoritmo Fuzzy C-Means foi a etapa mais desafiadora do projeto, exigindo o desenvolvimento do processo iterativo de atualização da matriz de pertinência e dos centroides. Para determinar o melhor valor do coeficiente de fuzzificação (m), foram realizados experimentos variando esse parâmetro entre 1.1 e 3.0, avaliando cada configuração por meio do coeficiente de Silhouette e de um score ponderado (Score = Silhouette × (1 − Proporção de Ruído)).

Conforme apresentado na **Figura 1**, embora o coeficiente de Silhouette apresente valores elevados para diferentes configurações, o aumento do parâmetro *m* também resulta em uma maior quantidade de amostras classificadas como ruído. Dessa forma, o score ponderado foi utilizado para selecionar automaticamente a configuração que apresentou o melhor equilíbrio entre qualidade dos agrupamentos e minimização dos ruídos, definindo m = 1.2 como o valor adotado.

<p align="center">
  <img src="imgs/Coeficiente de Silhouette (iris completa).png" width="850">
</p>

<p align="center">
  <em>Figura 1 – Avaliação do coeficiente de fuzzificação por meio do coeficiente de Silhouette, quantidade de ruídos e score ponderado.</em>
</p>

Após a definição do melhor valor para o coeficiente de fuzzificação, o algoritmo foi aplicado à base Iris. A **Figura 2** apresenta um pairplot contendo todas as combinações entre as variáveis do conjunto de dados, destacando a distribuição das amostras, os grupos formados pelo algoritmo e a posição dos centroides obtidos.

<p align="center">
  <img src="imgs/Pairplot com centróides.png" width="550">
</p>

<p align="center">
  <em>Figura 2 – Pairplot da base Iris com os agrupamentos obtidos pelo Fuzzy C-Means e seus respectivos centroides.</em>
</p>

## Equipe

Projeto desenvolvido em grupo para a disciplina de Aprendizado Não Supervisionado.

**Integrantes:**
- Edson Eduardo Ferreira - 23908965
- Gabriel Batista Chiezo - 23028678
- Yan Yoshida Luz - 23911118