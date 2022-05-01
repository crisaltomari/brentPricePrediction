# Predição de Preços do Óleo Cru usando Ferramenta de Machine Learning e Predição de Dados

#### Aluno: [Cristiane Altomari Teixeira](https://github.com/crisaltomari)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC)

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/crisaltomari/brentPricePrediction/blob/main/OilPricePredictionML.zip). <!-- caso não aplicável, remover esta linha -->


---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

Este trabalho tem como objetivo principal a previsão de preço do petróleo bruto utilizando a ferramenta ML.NET.

Para tanto, este trabalho foi construído utilizando os preços históricos consolidados trimestralmente de 2005 a 2021.

Esses dados foram divididos por treinamento e validação, proporcionalmente em 90% e 10% respectivamente.

Além disso, a ferramenta ML.NE foi utilizada para a predição de valor. Através da variação do tempo de treinamento, esta ferramenta criou cinco modelos com diferentes metodologias de previsão.


### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

This work has the major objective of the price prediction of oil crude using the ML.NET tool.

For that,  this work was constructed using the historical prices consolidated quarterly from 2005 to 2021. 

These data were split by training and validation,  proportionally by90% and 10% respectively. 

Furthermore,  the ML.NE tool was used for the value prediction. Through the training time variating,  this tool created five models  with different methodologies of prediction 

### 1. Introdução

O óleo cru é uma das matérias-primas mais relevantes no mundo moderno. Isto se deve ao fato de que é utilizado como fonte de energia e seus derivados podem ser transformados em plástico, borracha sintética, tintas, corantes, adesivos, solventes, detergentes, produtos farmacêuticos, cosméticos, entre outras aplicações.

Por conta das suas aplicabilidades, tornou-se um recurso básico e indispensável nos dias de hoje e o seu preço influencia diretamente a inflação de um dado país tendo a vista a dependência que eles possuem deste insumo.

Por ser uma commodity, o óleo cru tem o seu preço influenciado por pelo balanço de oferta e demanda e dados econômicos conforme ilustrado na figura abaixo:

![imagem1](./Figura%201-%20Fatores%20que%20influenciam%20o%20pre%C3%A7o%20do%20%C3%B3leo%20cru.png)

Segundo U.S Energy Information Administration (EIA), os principais fatores que impactam o preço dessa commodity estão correlacionados conforme ilustrado na figura abaixo:  

!imagem2](./Figura%202%20-%20U.S%20Energy%20Information%20Administration%20(EIA).png)

• Eventos Geopolíticos e Econômicos

O preço do óleo cru acompanha os eventos econômicos e geopolíticos. Possíveis conflitos com as principais nações produtoras de óleo cru podem acarretar sérios problemas no suprimento dessa commodity, desbalançando os estoques e alterando, por conseguinte, o preço do petróleo.

![imagem3](./Figura%203%20-%20U.S.%20Energy%20Information%20Administration%2C%20Refinitiv%20An%20LSEG%20Business.png)

Isso se deve ao fato de que o consumo de óleo cru é impactado pelo crescimento econômico:

![imagem4](./Figura%204%20-%20U.S.%20Energy%20Information%20Administration%2C%20Oxford%20Economics.png]

Diante disso, expectativas no crescimento econômico afetam o preço do óleo cru:

![imagem5](./Figura%205%20-%20%20Oxford%20Economics.png)

• Oferta de Produto

A oferta está relacionada com a quantidade de óleo cru disponível ao redor do mundo. Historicamente, a oferta tem sido determinada pelos países membros da OPEP+; contudo, os Estados Unidos vêm desempenhando um papel maior no fornecimento, graças à produção em expansão dos seus campos de xisto. Sendo assim, a oferta de óleo cru é alto à medida que os principais países produtores aumentam a sua produção.

O gráfico abaixo explifica tal fato ao mostrar que interrupções não planejadas no fornecimento do óleo cru pressionam o incremento de preço.

![imagem6](./Figura%206%20-%20U.S.%20Energy%20Information%20Administration.png)

• Demanda de Produto

A demanda, por outro lado, é intrinsecamente relacionada a todas as suas aplicabilidades de óleo cru em um dado momento, tais como, para geração de eletricidade, aquecimento e transporte. Assim, quanto maior o crescimento econômico de uma dada região, maior será a demanda por óleo cru.

Diante do exposto, é possível notar na figura abaixo o aumento preço associado ao crescimento da demanda mundial.



![imagem7](./Figura%207-%20Short-Term%20Energy%20Outlook.png)

Por conta da sua importância econômica e social e dos impactos no custo dessa commodity, foi desenvolvida uma ferramenta de predição de preço do óleo cru a qual será detalhada nos próximos capítulos.



### 2. Modelagem

A partir da coleta de todos os dados públicos trimestrais registrados das variáveis que influenciam o preço do óleo cru (variáveis listadas na Figura 1), escolheu-se seguir com a estratégia de uso de um conjunto de ferramentas disponibilizadas pela Microsoft dentro da plataforma de desenvolvimento Visual Studio, chamado ML.NET. Esta ferramenta permite o desenvolvimento de diferentes modelos de Machine Learning, incluindo predi
cão de valores, usada neste trabalho. Para isto, a partir das informações coletadas, criou-se dois grupos de dados:

- Dados para treinamento do sistema de predição do preço do óleo cru (aproximadamente 90% do volume dos dados coletados)
- Dados para validação dos modelos de predição desenvolvidos para o preço do óleo cru (aproximadamente 10% do volume dos dados coletados)

De posse do conjunto de dados de treinamentos, usou-se a ferramenta de criação de modelos de predição de valores, definindo qual variável se desejaria realizar predição e confirmando o tipo de informações das demais variáveis. Por exemplo, a variável trimestre, apesar de ser numérica, foi tratada como string por ser categorica.

Com o ML.NET, o sistema realiza os testes e verificações dos principais parâmetros de performance de predição para um grande leque de modelos de regressão, tendo como principal variável de entrada para o usuário o tempo de treinamento.

Assim, o sistema, ao final do tempo de treinamento definido inicialmente, seleciona o melhor método de regressão com base nos melhores resultados que medem a performance do modelo.

Desta forma, rodou-se 5 simulações, construindo 5 modelos diferentes, cada qual usando um tempo de treinamento distinto (crescente). Cada modelo, selecionou o método de regressão mais adequado, podendo ser igual ao método selecionado em uma simulação passada, mas chegando a paâmetros de performance distintos.

Ao criar um modelo, é possível testá-lo (a própria interface do Visual Studio e do ML.NET permitem tal teste). Com isso, foi-se usado o conjunto de dados de validação, para testar os 5 modelos e assim determinar o erro percentual de cada um deles.

### 3. Resultados

Os resultados obtidos das 5 simulações e desenvolvimentos de modelos encontram-se disponíveis no arquivo:

https://github.com/crisaltomari/brentPricePrediction/blob/main/medium_variablesxlsx.xlsx

Os resultados mostraram um um baixo tempo de treinamento produziu um modelo com erro médio de 14% enquanto que modelos com tempo de treinamento a partir de 150 segundos, produziu modelos com erros médios entre 7 e 8%.

Os dados foram obtidos diretamente dos cálculos executados pela ferramenta ML.NET e tratados em MS Excel para comparação e validação dos modelos (dados reais vs dados calculados como predição).

Os melhores métodos de regressão e predição identificados pelo ML.NET para os dados utilizados foram:

FastTreeTweedieRegression
LbfgsPoissonRegressionRegression

Observou-se que a partir de 150s de tempo de treinamento, apesar de obter melhores resultados de R^2, o erro médio foi praticamente o mesmo entre tempos de treinamento de 150s a 3600s.



### 4. Conclusões

A partir dos resultados encontrados, pôde-se verificar que a ferramenta de predição de dados contida no pacote ML.NET se mostrou uma excelente opção para criação de modelos com este fim.

Mesmo com poucos dados disponíveis (mesmo usando todos os dados desde o início em que eles começaram a ser registrados, os dados ainda eram trimestrais), o sistema conseguiu desenvolver modelos com erro percentual médio de 7% e desvio padrão de 0,185203.

Este erro é considerado bem baixo e o tempo necessário de treinamento para obter um modelo com tal erro foi de apenas 3600s e não foi necessário uso de GPUs dedicadas de processamento para o desenvolvimento deste modelo.

Assim, este trabalhou mostrou que além da ferramenta usada ser bastante útil e factível, mostrou também que os dados disponibilizados pela EIA podem ser usados para criar modelos matemáticos que reflitam o relacionamento dos dados e assim usá-los para predição de informações, melhorando e otimizando o processo de tomada de decisão.

---

Matrícula: 123.456.789

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
