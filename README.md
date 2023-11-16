<div align="center">
  <h1>Ilum - Escola de Ciência</h1>
</div>

<div align="center">
  <h2> Predição de secas usando dados de solo e clima </h2>
</div>

<div align="center">
  <h3> Grupo Zeta </h3>
</div>

<div align="center">
  <h4>  
  Anna Karen Pinto;
  Beatriz Borges;
  Daniel Bravin; 
  Paulo Henrique dos Santos
  </h4>
</div>

<div align="center">
  <h5> Campinas/2023 </h5>
</div>


# Resumo  

Este trabalho visa explorar e propor um modelo de aprendizado de máquina destinado a identificar correlações entre diversas condições climáticas, incluindo temperatura, velocidade dos ventos, nível de umidade atmosférica, temperatura da superfície, precipitação e outros fatores relevantes. O objetivo principal é utilizar modelos de predição a partir das análises de dados climáticos, comparando-os, para predizer níveis de secas. 

Destaca-se que este projeto é desenvolvido como produto da disciplina de Machine Learning, integrante do curso de Bacharelado em Ciência e Tecnologia, oferecido pela Universidade ILUM-Escola de Ciência, instituição acadêmica vinculada ao CNPEM (Centro Nacional de Pesquisa em Energia e Materiais). 

# Importando Dados 

* Baixe o arquivo intitulado "Trabalho_Machine_Learn.ipynb" desse github.
* Acesse o link <https://www.kaggle.com/datasets/cdminix/us-drought-meteorological-data/data>.[1].
* Baixe a arquivo com o dataset. 
* Da pasta baixada, deverá selecionar o arquivo intitulado 'validation_timeseries.csv' e colocá-lo na mesma pasta na qual o arquivo "Trabalho_Machine_Learn.ipynb".
* Não é necessario remenomear o arquivo de dados. 

# Lista de Abreviaturas e Siglas

PCA (Principal Component Analysis)

O dataset utilizado contém os seguintes atributos:

WS10M_MIN = Velocidade do vento mínima a 10 metros (m/s)

QV2M = Humidade específica a 2 metros (g/kg)

T2M_RANGE = Faixa de temperatura a 2 metros (C)

WS10M = Velocidade do vento a 10 metros (m/s)

T2M = Temperatura a 2 metros (C)

WS50M_MIN = Velocidade do vento mínima a 50 metros (m/s)

T2M_MAX = Temperatura máxima a 2 metros (C)

WS50M = Velocidade do vento a 50 metros (m/s)

TS = Temperatura da crosta da Terra (C)

WS50M_RANGE = Faixa de velocidade do vento a 50 metros (m/s)

WS50M_MAX = Velocidade do vento máxima a 50 metros (m/s)

WS10M_MAX = Velocidade do vento máxima a 10 metros (m/s)

WS10M_RANGE = Faixa de velocidade do vento a 10 metros (m/s)

PS = Pressão da superfície (kPa)

T2MDEW = Ponto de orvalho a 2 metros (C)

T2M_MIN = Temperatura mínima a 2 metros (C)

T2MWET = Temperatura do termômetro Wet Bulb a 2 metros (C)

PRECTOT = Precipitação (mm; dia-1)

score = Medidas de seca (0-5; a cada 7 dias)

date = Data da medida

fips = Padrões emitidos para garantir segurança e interoperabilidade de computador em sistemas de criptografia (referente a locais dos EUA) [6]

# Introdução

A predição de secas é um problema crítico em muitas partes do mundo, pois as secas podem causar impactos devastadores na agricultura, no abastecimento de água e no meio ambiente. Portanto, é fundamental entendermos como antecipar a ocorrência de secas, permitindo a implementação de medidas preventivas e o planejamento adequado, incentivando um investimento tecnológico e científico maior nesta área. 

Os dados sobre solo e clima desempenham um papel fundamental na compreensão e predição de secas. As características do solo, como o teor de umidade, a textura e a composição química, afetam diretamente a capacidade do solo de reter água e suportar a vegetação. Além disso, as condições climáticas, como a precipitação, a temperatura e a umidade do ar, têm um impacto direto na quantidade de água disponível no solo. 

A ciência que é utilizada para esta problemática é o Aprendizado de Máquina (Machine Learning), que é um subconjunto da Inteligência Artificial (IA) o qual permite que um sistema aprenda e melhore de forma autônoma usando redes neurais e aprendizado profundo, sem ser programado explicitamente, alimentando-o com grandes quantidades de dados. [2] Dessa forma, seria viável programar um algoritmo que tivesse os dados de solo e clima como entrada (input), e retornasse uma saída (output) da previsão de seca. 

Esses dados podem ser coletados de diversas formas possíveis, variando de acordo com sua finalidade e recursos para a pesquisa. Entretanto, algo em comum com todo qualquer tipo de dado é que eles são armazenados em dataset. 

Dataset é um conjunto de dados estruturados em uma tabela, contendo descrições específicas de seus atributos e arquivos significativos para o conjunto. [3] Com o conjunto de dados, é possível extrair informações necessárias para a aplicação/manipulação desejada.

Ao utilizar um dataset que combina dados de solo e clima, pode-se desenvolver modelos de Machine Learning mais robustos e precisos. Esses modelos podem capturar correlações complexas entre as variáveis ambientais e, assim, melhorar a capacidade de prever secas com antecedência. 

A escolha desse tipo de dataset permite uma abordagem multidisciplinar, integrando conhecimentos, sem perder a importância científica proposta pelo trabalho final.

Este dataset não existiria sem a disponibilização pública desses dados oferecidos pela NASA POWER Project (Projeto POWER da NASA) e pelos autores da US Drought Monitor (Monitor de Seca dos EUA). [1] [4] [5].

# Metodologia
Inicialmente, procedeu-se com a importação das bibliotecas necessárias e dos dados, os quais estavam subdivididos em conjuntos, de validação, treino e teste. Essa etapa visava preparar o terreno para uma análise exploratória a fim de compreender melhor os componentes dos dados e definir os passos subsequentes. Assim, decidiu-se utilizar apenas o subconjunto de validação devido à grande quantidade de dados disponíveis.

Durante a análise detalhada, identificou-se que o conjunto continha mais de 40 milhões de registros, caracterizando-se como bigdata. Essa natureza dos dados apresentou desafios significativos em termos de complexidade e exigiu habilidades específicas. Além disso, devido a estrutura e caracterização dos dados, um modelo de previsão utilizando séries temporais também seria possível. É importante ressaltar que o tratamento de séries temporais não estava previsto no conteúdo programático da disciplina, mas a natureza flexível do dataset permitiu a liberdade de uma interpretação fora desse contexto. Portanto, o contexto da análise temporal dos dados (datação) não foi um atributo principal da predição, contudo o atributo data foi desmembrado e utilizado como alguns dos vários atributos no modelo de predição. 

Durante o processo, também foi constatada a presença de valores nulos (NaN), os quais foram exclusivamente encontrados na coluna "score" devido à coleta de dados em intervalos de sete dias. Esses valores foram removidos. A coluna "fips" (Federal Information Processing Standards), que representa os padrões desenvolvidos pelo National Institute of Standards and Technology, foi analisada para contabilizar o número de locais distintos catalogados nos dados, com o intuito de estabelecer relações entre indicadores climáticos. Entretanto, devido a esse propósito específico, a decisão tomada foi a remoção da coluna, uma vez que a análise parcial das regiões não era um objetivo.

Além disso, procedeu-se à identificação e eliminação de valores anômalos por meio do método de detecção de outliers utilizando o desvio padrão. Este método envolve a avaliação da distância de um dado específico em relação à média geral dos dados, sendo essa distância medida em unidades de desvio padrão.

A coluna "data" foi desmembrada em três novas colunas ("day", "month" e "year"), como dito anteriormente.

A partir desse ponto, trabalhou-se com três tipos distintos de conjuntos de dados, cada um submetido a diferentes métodos de seleção de atributos:

* Primeiro dataset: Este conjunto foi submetido a uma análise de multicolinearidade (Seleção VIF - Variance Inflation Factor).
* Segundo dataset: O segundo conjunto foi redimensionado utilizando o método PCA (Principal Component Analysis), cuja principal função é verificar a quantidade de atributos que influenciam num determinado sistema.
* Terceiro dataset: O terceiro conjunto foi submetido a ambos os métodos de seleção de atributos.
  
A escolha de realizar essa separação teve como objetivo determinar a ferramenta de seleção de atributos mais eficaz para o conjunto de dados escolhido, considerando as predições a serem realizadas. Após essa fase, os conjuntos foram divididos em treino e teste, dando início ao processo de realização das predições.

### Modelos de predição utilizados

Existem vários modelos de predição disponíveis para uso. A escolha dos modelos abaixo foi baseada na premissa de avaliar como cada um reagia diante dos novos datasets. Cada modelo foi testado com os conjuntos de dados recém-criados, buscando realizar uma comparação de eficiência entre eles.

**Modelo KNN**

Em síntese, o algoritmo KNN (K-Nearest Neighbors) busca classificar cada amostra de um conjunto de dados ao avaliar sua proximidade em relação aos vizinhos mais próximos. Caso a maioria desses vizinhos pertença a uma determinada classe, a amostra em análise será classificada nessa categoria específica. Este método fundamenta-se na ideia de que objetos semelhantes tendem a estar próximos uns dos outros no espaço de características, facilitando a atribuição de rótulos com base na predominância das classes dos vizinhos mais próximos.[7].

**Árvore de Decisão**

Conforme indicado pelo próprio nome, o algoritmo cria vários pontos de decisão, representados como "nós" na árvore. Em cada nó, a decisão é tomada para seguir por um caminho específico. Esses caminhos são representados pelos "ramos". Essa estrutura fundamental de uma árvore de decisão desempenham o papel de conferenciar e indicar o direcionamento para os ramos subsequentes do fluxo de decisão.[10].

**Floresta Aleatória**  

A Floresta Aleatória, um algoritmo de aprendizagem supervisionada, cria uma "floresta" composta por uma combinação (ensemble) de árvores de decisão, frequentemente treinadas por meio do método de bagging. A essência do bagging reside na ideia central de que a fusão de modelos de aprendizado contribui para uma melhoria no resultado global.

Uma vantagem da Floresta Aleatória é sua aplicabilidade tanto em tarefas de classificação quanto em tarefas de regressão, abrangendo a maioria dos sistemas atuais de aprendizado de máquina.[11].

 *SMOTE*

O SMOTE opera com a proposta fundamental de gerar exemplos sintéticos para a classe minoritária, visando ampliar sua representação no conjunto de dados. Esse processo envolve a criação de instâncias "sintéticas" entre pares de instâncias da classe minoritária. A técnica, por sua vez, calcula a diferença entre uma instância da classe minoritária e seus vizinhos mais próximos, gerando novas instâncias ponderadas por essa diferença.

O SMOTE não é um modelo preditivo em si, mas sim uma ferramenta projetada para equilibrar a quantidade de dados no conjunto. No conjunto de dados utilizado sua aplicação combinou-se com uma segunda floresta aleatória. Esse procedimento serve para verificar se a introdução de dados sintéticos no conjunto de dados produz impactos significativos.

# Resultados e Discussões

As comparações de eficiência entre os modelos de predição foram conduzidas por meio do Score. De maneira geral, o termo "score" em modelos de classificação refere-se a métricas que avaliam o desempenho do modelo na tarefa de atribuir rótulos de classe a amostras. Essas métricas são utilizadas para quantificar quão bem o modelo está fazendo suas previsões. Quanto mais próximo de 1 é o valor da quantificação, melhor o modelo.

Ao explorar os modelos de previsão nos três conjuntos de dados distintos, pode-se ter uma compreensão da precisão de suas predições.

Conforme mencionado anteriormente, há três conjuntos de dados, cada um tratado de maneiras diferentes. Três modelos distintos foram aplicados a cada conjunto de dados para comparação, e constatou-se que, para o modelo KNN, o conjunto de dados, ao ser analisado com o SCORE, que obteve a melhor pontuação foi aquele tratado apenas com VIF, alcançando uma precisão de 821.59. Os demais conjuntos, tratados apenas com PCA, obtiveram uma pontuação de 795.9, enquanto aqueles que receberam tratamento tanto de VIF quanto de PCA registraram uma pontuação de 795.9.

Para o modelo de Árvore de Decisão, ao analisar o SCORE, o conjunto de dados que obteve a melhor pontuação foi aquele tratado apenas com VIF, alcançando uma precisão de 0.802. Os demais conjuntos, tratados apenas com PCA, registraram uma pontuação de 0.793, enquanto aqueles que receberam tratamento tanto de VIF quanto de PCA obtiveram uma pontuação de 0.787.

Para o modelo de Floresta Aleatória, ao examinar o SCORE, o conjunto de dados que apresentou o desempenho mais destacado foi aquele tratado exclusivamente com VIF, atingindo uma precisão de 0.846. Nos outros conjuntos, que foram submetidos apenas ao PCA, a pontuação foi de 0.831, enquanto aqueles que receberam tratamento tanto de VIF quanto de PCA registraram um SCORE de 0.831. 

Os modelos de Floresta Aleatória, após o tratamento com SMOTE, apresentaram resultados idênticos para os três conjuntos de dados.

# Conclusão

Os resultados obtidos ao explorar diferentes modelos de predição em conjuntos de dados tratados de maneiras distintas revelaram curiosidades sobre o desempenho desses algoritmos. Como visto, para o algoritmo KNN, o conjunto de dados tratado exclusivamente com VIF demonstrou uma precisão superior, destacando a eficácia desse método específico de tratamento. Já para o algoritmo de Árvore de Decisão e Floresta Aleatória, observou-se que o tratamento com VIF também proporcionou um desempenho superior, evidenciando a influência positiva desse método nesse contexto.

É interessante notar que, ao aplicar o SMOTE aos modelos de Floresta Aleatória, os resultados foram consistentes entre os conjuntos de dados, indicando que essa técnica de balanceamento não teve um impacto diferenciado nos conjuntos analisados.

A escolha adequada do método de tratamento de dados e do algoritmo pode ter um impacto significativo no desempenho dos modelos de Machine Learning. Cada abordagem tem suas vantagens e pode ser mais apropriada dependendo das características específicas do conjunto de dados e dos objetivos da análise. A análise cuidadosa desses resultados permite tomar decisões mais informadas na escolha e otimização de modelos para tarefas futuras.

Portanto o melhor modelo para o conjunto de dados proposto nesse trabalho é o modelo de Floresta Aleatória com dados tratados com VIF. 

# Planos futuros

* Tentar abordar o mesmo dataset, porém agora com séries temporais para entender como funciona esse método de predição e como os dados se comportam diante disso;
* Utilizar o mesmo modelo em dados brasileiros;

# Curiosidades

Ao conduzir a validação cruzada em todos os modelos, independentemente de aplicar o PCA ou a validação VIF, os hiperparâmetros otimizados pela validação cruzada permanecem consistentes. Essa consistência sugere uma estabilidade nos hiperparâmetros identificados, independentemente do método específico de tratamento de dados escolhido.
Será se isso persiste em outros datasets ou apenas no nosso?

# Referências

[1] Predict Droughts using Weather & Soil Data. Disponível em: <https://www.kaggle.com/datasets/cdminix/us-drought-meteorological-data/data>. Acesso em: 11 nov. 2023.

[2] O que é Machine Learning?  |  Google Cloud. Disponível em: <https://cloud.google.com/learn/w hat-is-machine-learning?hl=pt-br>. Acesso em: 11 nov. 2023.

[3] Dados estruturados de conjunto de dados | Central da Pesquisa Google | Documentação. Disponível em: <https://developers.google.com/search/docs/appearance/structured-data/dataset?hl=pt-br>. Acesso em: 11 nov. 2023.

‌
[4] NASA. NASA POWER | Prediction Of Worldwide Energy Resources. Disponível em: <https://power.larc.nasa.gov/>. Acesso em: 11 nov. 2023.

‌
[5] Contact Us | U.S. Drought Monitor. Disponível em: <https://droughtmonitor.unl.edu/About/ContactUs.aspx>. Acesso em: 11 nov. 2023.

‌
[6] Federal Information Processing Standards. Disponível em: <https://pt.wikipedia.org/wiki/Federal_Information_Processing_Standards>. Acesso em: 11 nov. 2023.

[7] "O que é e como funciona o algoritmo KNN" | Didática Tech. Disponível em: <https://didatica.tech/o-que-e-e-como-funciona-o-algoritmo-knn/>. Acesso em: 15 nov. 2023.

[8] "sklearn.neighbors.KNeighborsClassifier" | scikit-learn | Documentação. Disponível em: <https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html>. Acesso em: 15 nove. 2023.

[9] "sklearn.pipeline.Pipeline" | scikit-learn | Documentação. Disponível em: <https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html>. Acesso em: 15 nov. 2023.

[10] "Como funciona o algoritmo Árvore de Decisão" | Didática Tech. Disponível em: <https://didatica.tech/como-funciona-o-algoritmo-arvore-de-decisao/>. Acesso em: 15 nov. 2023.

[11]  "O Algoritmo da Floresta Aleatória" | Medium - Machina Sapiens. Disponível em: <https://medium.com/machina-sapiens/o-algoritmo-da-floresta-aleat%C3%B3ria-3545f6babdf8>. Acesso em: 15 nov. 2023.

