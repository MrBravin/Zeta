# Grupo Zeta
Integrantes: 
  Anna Karen Pinto;
  Beatriz Borges;
  Daniel Bravin; e
  Paulo Henrique dos Santos
  

Esse trabalho tem objetivo de estudar e propor um modelo de aprendizado de maquina capaz de estabelecer relações entre condições climáticas, tais como: temperatura, velocidade dos ventos, nível de umidade atmosférica, temperatura da superfície, precipitação e alguns outros. De entender como as variações climáticas progrediram através dos anos e estabelecer possíveis previsões. 

Banco de Dados pode ser acessado através do link: https://drive.google.com/file/d/1t3dj_g1M8-sX_Siqc36_rSp_UACnj_bL/view?usp=drive_link

# Introdução

A predição de secas é um problema crítico em muitas partes do mundo, pois as secas podem causar impactos devastadores na agricultura, no abastecimento de água e no meio ambiente. Portanto, é fundamental entendermos como antecipar a ocorrência de secas, permitindo a implementação de medidas preventivas e o planejamento adequado, incentivando um investimento tecnológico e científico maior nesta área. 

Os dados sobre solo e clima desempenham um papel fundamental na compreensão e predição de secas. As características do solo, como o teor de umidade, a textura e a composição química, afetam diretamente a capacidade do solo de reter água e suportar a vegetação. Além disso, as condições climáticas, como a precipitação, a temperatura e a umidade do ar, têm um impacto direto na quantidade de água disponível no solo. 

A ciência que é utilizada para esta problemática é o Aprendizado de Máquina (Machine Learning), que é um subconjunto da Inteligência Artificial (IA) o qual permite que um sistema aprenda e melhore de forma autônoma usando redes neurais e aprendizado profundo, sem ser programado explicitamente, alimentando-o com grandes quantidades de dados. [2] Dessa forma, seria viável programar um algoritmo que tivesse os dados de solo e clima como entrada (input), e retornasse uma saída (output) da previsão de seca no local analisado. 

Esses dados podem ser coletados de diversas formas possíveis, variando de acordo com sua finalidade e recursos para a pesquisa. Entretanto, algo em comum com todo qualquer tipo de dado é que eles são armazenados em dataset. 

Dataset é um conjunto de dados estruturados em uma tabela, contendo descrições específicas de seus atributos e arquivos significativos para o conjunto. [3] Com o conjunto de dados, é possível extrair informações necessárias para a aplicação/manipulação desejada.

Ao utilizar um dataset que combina dados de solo e clima, pode-se desenvolver modelos de Machine Learning mais robustos e precisos. Esses modelos podem capturar correlações complexas entre as variáveis ambientais e, assim, melhorar a capacidade de prever secas com antecedência. 

A escolha desse tipo de dataset permite uma abordagem multidisciplinar, integrando conhecimentos, sem perder a importância científica proposta pelo trabalho final.

Os dados usados para a predição foram retirados da referência [1].

# Metodologia

Analise exploratória

Ao realizar uma análise detalhada dos dados, constatou-se que o conjunto continha mais de 40 milhões de registros e caracterizava-se como séries temporais, o que apresentava desafios significativos em termos de complexidade e exigência de habilidades, especialmente dentro do escopo da disciplina em questão. Diante dessa situação, decidiu-se trabalhar com uma fração representativa dos dados, optando por utilizar apenas 1/7 (um sétimo) do conjunto. Essa escolha foi fundamentada no fato de que os dados relacionados à seca eram coletados em intervalos de sete dias. Entretanto, é importante destacar que o tratamento de séries temporais não estava contemplado no conteúdo programático da disciplina, mas o dataset estudado permite a liberdade de interpretação fora do campo de séries temporais. Assim, optou-se por conduzir a análise sem levar em consideração essa particularidade, o que reforça a justificativa para a escolha de trabalhar com um subconjunto reduzido de dados. Além disso, observou-se que as informações incluíam registros de diversas localidades, decidiu-se remover as colunas relacionadas à data e localidade.

Multicolinearidade



smoth

# Resultados e Discussões

# Conclusão

# Referências

[1] https://www.kaggle.com/datasets/cdminix/us-drought-meteorological-data/data

[2] https://cloud.google.com/learn/what-is-machine-learning?hl=pt-br

[3] https://developers.google.com/search/docs/appearance/structured-data/dataset?hl=pt-br

OBS: README, temporário.
