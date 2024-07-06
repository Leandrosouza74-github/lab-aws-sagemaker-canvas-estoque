
# 👀: Previsão de Estoque Inteligente (AWS) 

##### By Leandro Souza 
###### www.linkedin.com/in/leandro-souza-silva-75708614

## Descritivo:

Utilizando Inteligência Artificial, mais especificamente técnicas de Machine Learning, é possível prever o estoque futuro de um produto específico ao utilizar dados de todos os produtos de um negócio. Isso proporciona uma vantagem competitiva significativa, permitindo uma gestão de estoque mais eficiente e uma capacidade melhorada de atender à demanda de mercado de forma preditiva e precisa.

##### ********************************************************************************

## 🥅: Objetivos Deste Desafio de Projeto

Desenvolver habilidades e aplicar conhecimentos práticos na área de previsão de estoque de produtos.

##### ********************************************************************************

Etapas envolvidas:

##### ********************************************************************************

![Imagem](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/339880256-72f5c21f-5562-491e-aa42-2885a3184650.png?raw=true)

##### ********************************************************************************

## 🚶: Passo a Passo

### 🖋️:1. Selecionar Dataset 

-   O Dataset é o nome dado para a planilha de estoque de produtos do seu negócio. Geralmente feita no Excel.
  
  Apenas esse dataset será utilizado para a construção do modelo de IA Machine Learning, logo após a conclusão, será treinado e colocado para realizar as previsões.

-   Abaixo está a imagem do dataset escolhido dentre outros.

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ.png?raw=true)

##### ********************************************************************************
    
-   Visualização das 10 primeiras linhas do arquivo (Dataset).
  
    Como visto abaixo, foi feito um arquivo simples no Excel com poucas colunas de dados onde na coluna ID estão cada produto do estoque. Também temos a data, o preço e a quantidade no estoque.
    A contrário do que muitos pensam, quanto mais dados e colunas na planilha ou quanto mais se repetir os produtos variando seus dados e/ou quanto mais produtos diferentes mais padrões serão encontrados no treinamento do modelo, resultando maior precisão .

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/blob/main/paint/PDPQ%2010primeiras%20linhas.png?raw=true)

##### ********************************************************************************

### 🏚️: 2. Construir/Treinar

-   Configuração das variáveis de entrada e saída de acordo com os dados.
  
    Na entrada da rede de Inteligência Artificial que estamos construindo colocaremos os dados de cada coluna e na saída da rede sairá a previsão do estoque.
    
##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/6b187c9e-80b4-4498-a281-6426f503f8ad)

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/73d678b5-bbf9-4e95-930e-4d2ad0be978a)

##### ********************************************************************************

-   Início do treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

    O treinamento da rede é a etapa seguinte a da construção, é quando a rede, que você construiu de acordo com os dados dos produtos da planilha, vai "pensar" em como achar os padrões de forma mais eficiente possível, nesse ambiente que é o mundo dos dados.
    No nosso caso aqui vai levar uns 14 minutos, observando que temos uma planilha com mais de mil produtos diferentes.

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/3a599a6d-7a65-4a36-a622-4839fe3b9dfa)

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/2df11b4e-04ac-4e9d-b8eb-3ddbecc9018f)

##### ********************************************************************************

### 🧠: 3. Analisar

-   Após o treinamento, as métricas de performance do modelo foram as seguintes:

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/f6faf5a0-4d16-414f-8afe-7cf0c6021c85)

##### ********************************************************************************

-   Observação:

    É importante saber interpretar as métricas de performance, portanto é necessário um conhecimento básico de probabilidade do erro  que qualquer um pode aprender rápido.Pensando nisso deixarei aqui tudo o que se precisa para este caso da previsão do estoque bem mastigado.

##### ----------------------------------------------------------------------------------


#### 🔥: Interpretação das Métricas
Quanto menor o valor do Avg. wQL, MAPE, WAPE, RMSE e MASE, melhor é o desempenho do modelo, pois indicam menores erros em relação aos dados reais.
Cada métrica oferece uma perspectiva diferente sobre a precisão do modelo, sendo importante considerar várias métricas para obter uma visão abrangente do desempenho.

##### ********************************************************************************

### 🚙: Vamos explanar um pouco mais sobre cada métrica:

#### Avg. wQL (Average Weighted Quantile Loss):

Esta métrica avalia a precisão das previsões em diferentes quantis da distribuição dos dados. É uma medida de erro que leva em consideração a distribuição dos erros em várias partes dos dados.

Um quantil é um valor que divide uma distribuição de dados em partes iguais ou em partes com proporções específicas, como medianas, quartis e percentis.

##### ********************************************************************************

##### Para calcular o Average Weighted Quantile Loss (Avg. wQL), você precisa seguir estes passos:

_ Definir os Quantis: Escolher os quantis da distribuição dos dados que deseja avaliar.

_ Ordenar os Erros: Ordenar os erros de previsão por quantil.

_ Atribuir Pesos: Atribuir pesos aos quantis com base na importância relativa.

_ Calcular o Erro Ponderado: Multiplicar os erros de previsão pelos pesos atribuídos.

_ Média dos Erros Ponderados: Calcular a média dos erros ponderados para obter o Avg. wQL.

##### ********************************************************************************

#### MAPE (Mean Absolute Percentage Error):

É a média do erro percentual absoluto, calculado como a média das diferenças absolutas entre os valores previstos e os valores reais, dividido pelos valores reais. É expresso como uma porcentagem.

##### ********************************************************************************

##### Para calcular o MAPE (Mean Absolute Percentage Error), siga estes passos:

1- Calcular o Erro Percentual Absoluto (APE) para cada observação:

Para cada par de observações (valor previsto e valor real), calcule o erro percentual absoluto (APE):

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/0e550863-c5ab-4327-b4ff-1680346369da)

2- Calcular a Média dos Erros Percentuais Absolutos (MAPE):

Depois de calcular o APE para cada observação, calcule a média desses valores para obter o MAPE:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/872fa25e-0341-467a-891e-a0c494bc0fe1)

##### ********************************************************************************

#### WAPE (Weighted Absolute Percentage Error):

É uma variação do MAPE que pondera os erros percentuais absolutos pela importância de cada observação. É útil quando há diferentes magnitudes de valores reais e é importante dar mais peso a determinadas observações.

##### ********************************************************************************

##### Para calcular o WAPE (Weighted Absolute Percentage Error), siga estes passos:

1- Calcular o Erro Percentual Absoluto (APE) para cada observação:

Para cada par de observações (valor previsto e valor real), calcule o erro percentual absoluto (APE):

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/d49cc209-d692-41e0-9e2f-88a35f8fed0b)

2- Atribuir Pesos às Observações:

Atribua pesos às observações com base na importância relativa de cada uma. Isso pode ser determinado por critérios específicos do problema ou pela magnitude dos valores reais.

3- Calcular o Erro Ponderado (WAPE):

Multiplique o APE de cada observação pelo peso correspondente e calcule a média ponderada dos erros percentuais absolutos:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/0869fa86-122b-4aef-807f-f0cceb0764f9)

##### ********************************************************************************

#### RMSE (Root Mean Squared Error):

É a raiz quadrada da média dos quadrados dos erros entre valores previstos e reais. É uma medida de dispersão dos erros e fornece uma ideia de quão bem o modelo está ajustando os dados.

##### ********************************************************************************

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

##### ********************************************************************************

#### MASE (Mean Absolute Scaled Error):

É uma medida de erro escalada, que compara o erro médio absoluto do modelo com o erro médio absoluto de um modelo de referência na mesma série temporal. É útil para avaliar a precisão de modelos em séries temporais.

##### ********************************************************************************

##### Para calcular o MASE (Mean Absolute Scaled Error), siga estes passos:

1- Calcular o Erro Absoluto Médio (MAE) para o modelo em questão:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/2f989642-77cc-4330-a9ca-377ab2631a35)

2- Calcular o Erro Absoluto Médio para o modelo de referência:

Em seguida, calcule o erro absoluto médio para um modelo de referência simples. Isso pode ser um modelo ingênuo que usa a média histórica dos dados como previsão:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/4ee2e72d-608d-42ba-ba5d-30ca85e72a03)

3- Calcular o MASE:

Finalmente, calcule o MASE como a razão entre o MAE do modelo e o MAE do modelo de referência:

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/ab00fc87-a724-4ead-9ed5-198b3dbbcd7f)

##### ********************************************************************************

####   A principal característica que influenciou a previsão do estoque foi a do preço:

 ![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/d0ee6bb3-4367-47ae-a69d-7d75c2bd3029)


##### ********************************************************************************

### 🔥: 4. Prever

O modelo foi treinado com os dados de vários produtos contidos na planilha e foi utilizado para fazer previsões de estoque em produtos específicos.
  

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/e091edf3-9817-49cf-a508-426a74c6dce2)

##### ********************************************************************************

![image](https://github.com/Leandrosouza74-github/lab-aws-sagemaker-canvas-estoque/assets/173939321/39dfcb2e-d1e3-4dd6-b91f-6b8b36c017f6)


##### ********************************************************************************

### 📖: Resultados:
Como dito anteriormente, o modelo foi treinado com os dados de vários produtos contidos na planilha e foi utilizado para fazer previsões de estoque em produtos específicos e além disso, o modelo do SageMaker Canvas trouxe como resultado os parametros "p10, p50 e p90" que será comentado na sequência deste relatório. 

##### ********************************************************************************

#### P10, P50 e P90 :

##### ********************************************************************************

P10 (Percentil 10): Indica que 10% das previsões de estoque são iguais ou menores que esse valor. Em outras palavras, é o valor abaixo do qual está o 10º percentil das previsões de estoque. Pode ser interpretado como uma estimativa conservadora ou pessimista para o estoque.

##### ********************************************************************************

P50 (Percentil 50 ou Mediana): Representa o valor no qual metade das previsões de estoque são menores e metade são maiores. É uma medida de tendência central e indica o valor central das previsões de estoque.

##### ********************************************************************************

P90 (Percentil 90): Indica que 90% das previsões de estoque são iguais ou menores que esse valor. É uma estimativa que captura um nível mais otimista ou expansivo para o estoque.

##### ********************************************************************************

## ⚒️: Conclusão com aplicação prática:

### Exemplo Prático:
Suponha que você gerencie uma quitanda e utiliza um modelo de previsão para estimar o estoque desses produtos com base em dados históricos de vendas e sazonalidade.

##### ********************************************************************************

Dados de Exemplo:

##### ********************************************************************************

Limão:

P10: 50 unidades
P50 (Mediana): 100 unidades
P90: 150 unidades

##### ********************************************************************************

Abacaxi:

P10: 20 unidades
P50 (Mediana): 40 unidades
P90: 60 unidades

##### ********************************************************************************


Laranja:

P10: 30 unidades
P50 (Mediana): 60 unidades
P90: 90 unidades

##### ********************************************************************************


### 🥷: Aplicações Práticas:

##### ********************************************************************************


#### Planejamento de Compras:

Com base nos percentis, você pode planejar as compras de cada produto de acordo com o nível de estoque desejado e o risco de escassez. Por exemplo, para limões, garantir que sempre haja pelo menos 50 unidades (P10) pode ser uma estratégia conservadora para evitar falta de estoque.

##### ********************************************************************************


#### Gestão de Sazonalidade:

Durante períodos de alta sazonalidade, como no verão quando a demanda por limões e laranjas aumenta, você pode aumentar o estoque alvo para os percentis mais altos (P90), garantindo que haja um buffer suficiente para atender à demanda esperada.

##### ********************************************************************************


#### Decisões de Produção e Estoque:

Os percentis podem orientar decisões sobre produção e armazenamento. Por exemplo, se o P50 para abacaxis indica 40 unidades, você pode ajustar a produção para manter esse nível de estoque sem excesso de produtos perecíveis.

##### ********************************************************************************


#### 👁️: Previsão de Vendas:

Os percentis também ajudam na previsão de vendas futuras, permitindo ajustes dinâmicos no estoque com base em cenários de demanda esperada.

##### ********************************************************************************


#### 🧠: Conclusão final:

Os percentis P10, P50 e P90 são ferramentas poderosas para a gestão eficaz de estoque em uma quitanda ou qualquer negócio que lide com produtos perecíveis ou sazonais. Eles fornecem insights sobre a variabilidade das previsões de estoque e ajudam na tomada de decisões para garantir um equilíbrio entre oferta e demanda, minimizando o risco de excesso ou falta de estoque.

Geralmente, quanto maior e mais diversificada for a sua planilha de dados históricos, melhor serão as previsões de um modelo de previsão. Isso ocorre porque um modelo de machine learning pode aprender padrões mais complexos e representativos com uma quantidade maior de dados.

Aqui estão alguns benefícios de ter uma planilha mais extensa e diversificada:

Captura de Variações e Tendências: Com mais dados, o modelo pode capturar melhor as variações e tendências ao longo do tempo, permitindo previsões mais precisas.

Melhor Aprendizado do Modelo: Um modelo treinado com mais dados pode aprender relações mais sutis entre as variáveis (como preço, data e estoque), o que pode levar a previsões mais precisas e robustas.

Redução de Viés e Erro: Uma planilha maior e mais diversa pode ajudar a reduzir o viés e o erro do modelo, pois fornece uma representação mais completa do comportamento dos dados.

Flexibilidade e Generalização: Com uma base de dados mais ampla, o modelo pode generalizar melhor para novos dados e situações, aumentando sua capacidade de fazer previsões precisas em cenários variados.

### Portanto, é vantajoso expandir sua planilha com dados atualizados e repetir os registros existentes ao longo do tempo para melhorar a qualidade das previsões de estoque ou qualquer outro tipo de previsão que você esteja realizando.

##### ********************************************************************************


### Leandro Souza


