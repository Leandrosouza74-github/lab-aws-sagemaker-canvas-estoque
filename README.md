
# 👀: Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

##### ****************************************************************************************************************************************************

## 🥅: Objetivos Deste Desafio de Projeto

##### ****************************************************************************************************************************************************

![Imagem](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/339880256-72f5c21f-5562-491e-aa42-2885a3184650.png?raw=true)

##### ****************************************************************************************************************************************************

## 🚶: Passo a Passo

### 1. Selecionar Dataset 

-   Escolhido o datasets na pasta `datasets` deste repositório.
##### ****************************************************************************************************************************************************

Dataset--> [Produto,Data,Preço e Quantidade (PDPQ)](datasets/dataset-1000-com-preco-variavel-e-renovacao-estoque.csv)

##### ****************************************************************************************************************************************************

-   Upload do dataset foi feito com sucesso no SageMaker Canvas.

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ.png?raw=true)

##### ****************************************************************************************************************************************************
    
-   Visualização das 10 primeiras linhas do arquivo.

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%2010primeiras%20linhas.png?raw=true)

##### ****************************************************************************************************************************************************

### 2. Construir/Treinar

-   Configuração das variáveis de entrada e saída de acordo com os dados.

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/6b187c9e-80b4-4498-a281-6426f503f8ad)

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/73d678b5-bbf9-4e95-930e-4d2ad0be978a)

##### ****************************************************************************************************************************************************

-   Início do treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/3a599a6d-7a65-4a36-a622-4839fe3b9dfa)

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/2df11b4e-04ac-4e9d-b8eb-3ddbecc9018f)

##### ****************************************************************************************************************************************************

### 3. Analisar

-   Após o treinamento, as métricas de performance do modelo foram as seguintes:

##### ****************************************************************************************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/f6faf5a0-4d16-414f-8afe-7cf0c6021c85)

##### ****************************************************************************************************************************************************

#### Interpretação das Métricas
Quanto menor o valor do Avg. wQL, MAPE, WAPE, RMSE e MASE, melhor é o desempenho do modelo, pois indicam menores erros em relação aos dados reais.
Cada métrica oferece uma perspectiva diferente sobre a precisão do modelo, sendo importante considerar várias métricas para obter uma visão abrangente do desempenho.

##### ****************************************************************************************************************************************************

#### Utilização no SageMaker Canvas
No SageMaker Canvas, essas métricas são normalmente calculadas automaticamente após o treinamento do modelo. Você pode visualizar essas métricas na interface do Canvas, o que ajuda a entender como o modelo está performando e facilita a comparação entre diferentes configurações de modelos.

##### ****************************************************************************************************************************************************

### Vamos explanar um pouco mais sobre cada métrica:

#### Avg. wQL (Average Weighted Quantile Loss):

Esta métrica avalia a precisão das previsões em diferentes quantis da distribuição dos dados. É uma medida de erro que leva em consideração a distribuição dos erros em várias partes dos dados.

Um quantil é um valor que divide uma distribuição de dados em partes iguais ou em partes com proporções específicas, como medianas, quartis e percentis.

##### ****************************************************************************************************************************************************

##### Para calcular o Average Weighted Quantile Loss (Avg. wQL), você precisa seguir estes passos:

_ Definir os Quantis: Escolher os quantis da distribuição dos dados que deseja avaliar.

_ Ordenar os Erros: Ordenar os erros de previsão por quantil.

_ Atribuir Pesos: Atribuir pesos aos quantis com base na importância relativa.

_ Calcular o Erro Ponderado: Multiplicar os erros de previsão pelos pesos atribuídos.

_ Média dos Erros Ponderados: Calcular a média dos erros ponderados para obter o Avg. wQL.

##### ****************************************************************************************************************************************************

#### MAPE (Mean Absolute Percentage Error):

É a média do erro percentual absoluto, calculado como a média das diferenças absolutas entre os valores previstos e os valores reais, dividido pelos valores reais. É expresso como uma porcentagem.

##### ****************************************************************************************************************************************************

##### Para calcular o MAPE (Mean Absolute Percentage Error), siga estes passos:

1- Calcular o Erro Percentual Absoluto (APE) para cada observação:

Para cada par de observações (valor previsto e valor real), calcule o erro percentual absoluto (APE):

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/0e550863-c5ab-4327-b4ff-1680346369da)

2- Calcular a Média dos Erros Percentuais Absolutos (MAPE):

Depois de calcular o APE para cada observação, calcule a média desses valores para obter o MAPE:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/872fa25e-0341-467a-891e-a0c494bc0fe1)

##### ****************************************************************************************************************************************************

#### WAPE (Weighted Absolute Percentage Error):

É uma variação do MAPE que pondera os erros percentuais absolutos pela importância de cada observação. É útil quando há diferentes magnitudes de valores reais e é importante dar mais peso a determinadas observações.

##### ****************************************************************************************************************************************************

##### Para calcular o WAPE (Weighted Absolute Percentage Error), siga estes passos:

1- Calcular o Erro Percentual Absoluto (APE) para cada observação:

Para cada par de observações (valor previsto e valor real), calcule o erro percentual absoluto (APE):

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/d49cc209-d692-41e0-9e2f-88a35f8fed0b)

2- Atribuir Pesos às Observações:

Atribua pesos às observações com base na importância relativa de cada uma. Isso pode ser determinado por critérios específicos do problema ou pela magnitude dos valores reais.

3- Calcular o Erro Ponderado (WAPE):

Multiplique o APE de cada observação pelo peso correspondente e calcule a média ponderada dos erros percentuais absolutos:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/0869fa86-122b-4aef-807f-f0cceb0764f9)

##### ****************************************************************************************************************************************************

#### RMSE (Root Mean Squared Error):

É a raiz quadrada da média dos quadrados dos erros entre valores previstos e reais. É uma medida de dispersão dos erros e fornece uma ideia de quão bem o modelo está ajustando os dados.

##### ****************************************************************************************************************************************************

##### Para calcular o RMSE (Root Mean Squared Error), siga estes passos:

1- Calcular o Erro Quadrático para cada observação:

Para cada par de observações (valor previsto e valor real), calcule o erro quadrático:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/ea3def81-7cf6-494d-8055-aa0727a7de29)

2- Calcular a Média do Erro Quadrático (MSE):

Depois de calcular o erro quadrático para cada observação, calcule a média desses valores para obter o MSE:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/36993ee5-7223-41eb-837e-d087993cb1fb)

3- Calcular o RMSE:

Finalmente, calcule a raiz quadrada do MSE para obter o RMSE:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/9042aa63-e9fa-45ec-bd32-379ead44899b)

##### ****************************************************************************************************************************************************

#### MASE (Mean Absolute Scaled Error):

É uma medida de erro escalada, que compara o erro médio absoluto do modelo com o erro médio absoluto de um modelo de referência na mesma série temporal. É útil para avaliar a precisão de modelos em séries temporais.

##### ****************************************************************************************************************************************************

##### Para calcular o MASE (Mean Absolute Scaled Error), siga estes passos:

1- Calcular o Erro Absoluto Médio (MAE) para o modelo em questão:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/2f989642-77cc-4330-a9ca-377ab2631a35)

2- Calcular o Erro Absoluto Médio para o modelo de referência:

Em seguida, calcule o erro absoluto médio para um modelo de referência simples. Isso pode ser um modelo ingênuo que usa a média histórica dos dados como previsão:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/4ee2e72d-608d-42ba-ba5d-30ca85e72a03)

3- Calcular o MASE:

Finalmente, calcule o MASE como a razão entre o MAE do modelo e o MAE do modelo de referência:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/ab00fc87-a724-4ead-9ed5-198b3dbbcd7f)

##### ****************************************************************************************************************************************************

####   A principal características que influenciou a previsão do estoque foi a do preço:

 ![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/d0ee6bb3-4367-47ae-a69d-7d75c2bd3029)


##### ****************************************************************************************************************************************************

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

##### ****************************************************************************************************************************************************

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.

##### ****************************************************************************************************************************************************

