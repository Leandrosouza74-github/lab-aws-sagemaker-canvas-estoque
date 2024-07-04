
# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)


## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

## 🚀 Passo a Passo

### 1. Selecionar Dataset

-   Escolhido o datasets na pasta `datasets` deste repositório. 
-   Upload do dataset foi feito com sucesso no SageMaker Canvas.

### 2. Construir/Treinar

-   No SageMaker Canvas, importe o dataset que você selecionou.
-   Configure as variáveis de entrada e saída de acordo com os dados.
-   Inicie o treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

### 3. Analisar

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

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


