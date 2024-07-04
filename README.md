
# 👀: Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)


## 🥅: Objetivos Deste Desafio de Projeto

![Imagem](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/339880256-72f5c21f-5562-491e-aa42-2885a3184650.png?raw=true)

## 🚶: Passo a Passo

### 1. Selecionar Dataset 

-   Escolhido o datasets na pasta `datasets` deste repositório.
          Dataset--> [Produto,Data,Preço e Quantidade (PDPQ)](datasets/dataset-1000-com-preco-variavel-e-renovacao-estoque.csv)
    
-   Upload do dataset foi feito com sucesso no SageMaker Canvas.

    ![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ.png?raw=true)
    
-   Visualização das 10 primeiras linhas do arquivo.


![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%2010primeiras%20linhas.png?raw=true)

### 2. Construir/Treinar

-   Configuração das variáveis de entrada e saída de acordo com os dados.


![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%20treinamento.png?raw=true)
![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%20treinamento2.png?raw=true)

-   Início do treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.


![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%20treinamento3.png?raw=true)
![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%20analise.png?raw=true)

### 3. Analisar

-   Após o treinamento, as seguintes métricas de performance do modelo foram:


![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%20m%C3%A9tricas.png?raw=true)

#### Avg. wQL (Average Weighted Quantile Loss):

Esta métrica avalia a precisão das previsões em diferentes quantis da distribuição dos dados. É uma medida de erro que leva em consideração a distribuição dos erros em várias partes dos dados.


#### MAPE (Mean Absolute Percentage Error):

É a média do erro percentual absoluto, calculado como a média das diferenças absolutas entre os valores previstos e os valores reais, dividido pelos valores reais. É expresso como uma porcentagem.


#### WAPE (Weighted Absolute Percentage Error):

É uma variação do MAPE que pondera os erros percentuais absolutos pela importância de cada observação. É útil quando há diferentes magnitudes de valores reais e é importante dar mais peso a determinadas observações.


#### RMSE (Root Mean Squared Error):

É a raiz quadrada da média dos quadrados dos erros entre valores previstos e reais. É uma medida de dispersão dos erros e fornece uma ideia de quão bem o modelo está ajustando os dados.

#### MASE (Mean Absolute Scaled Error):

É uma medida de erro escalada, que compara o erro médio absoluto do modelo com o erro médio absoluto de um modelo de referência na mesma série temporal. É útil para avaliar a precisão de modelos em séries temporais.


-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

##### Interpretação das Métricas
Quanto menor o valor do Avg. wQL, MAPE, WAPE, RMSE e MASE, melhor é o desempenho do modelo, pois indicam menores erros em relação aos dados reais.
Cada métrica oferece uma perspectiva diferente sobre a precisão do modelo, sendo importante considerar várias métricas para obter uma visão abrangente do desempenho.

##### Utilização no SageMaker Canvas
No SageMaker Canvas, essas métricas são normalmente calculadas automaticamente após o treinamento do modelo. Você pode visualizar essas métricas na interface do Canvas, o que ajuda a entender como o modelo está performando e facilita a comparação entre diferentes configurações de modelos.

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.
#-----------------------------------------------------------------------------------------------------------------------------------------------------
# MINHAS OBSERVAÇÕES:

## Sobre o parâmetro MSE
Mean Squared Error (MSE) é a média dos quadrados dos erros, onde o erro é a diferença entre os valores observados e os valores previstos.

O MSE é sempre não negativo, e um valor de 0 indica que o modelo está prevendo perfeitamente os valores observados.

Valores Pequenos de MSE: Indicam que os valores previstos estão próximos dos valores reais.
Valores Grandes de MSE: Sugerem que há grandes diferenças entre os valores previstos e reais.

Como o MSE é a média dos quadrados dos erros, ele amplifica os grandes erros, penalizando fortemente as previsões que estão muito distantes dos valores reais.

## Sobre o parâmetro RMSE

Root Mean Squared Error (RMSE) é uma métrica que mede a precisão das previsões de um modelo. É a raiz quadrada da média dos quadrados das diferenças entre os valores previstos e os valores reais. Quanto menor o RMSE, mais preciso é o modelo.

Como o RMSE é a raiz quadrada do MSE, ele tem a mesma unidade dos valores previstos, tornando-o mais interpretável em termos das unidades dos dados.

Valores Pequenos de RMSE: Indicam que o modelo tem um desempenho bom em prever os valores observados.
Valores Grandes de RMSE: Sugerem que o modelo tem dificuldades em capturar as variações nos dados.

Ele também amplifica os grandes erros, mas como ele é uma raiz quadrada, a amplificação é menos severa do que no MSE.


