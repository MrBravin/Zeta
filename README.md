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

Este trabalho visa explorar e propor um modelo de aprendizado de máquina destinado a identificar correlações entre diversas condições climáticas, incluindo temperatura, velocidade dos ventos, nível de umidade atmosférica, temperatura da superfície, precipitação e outros fatores relevantes. O objetivo principal é compreender a evolução das variações climáticas ao longo dos anos e, a partir dessas análises, formular previsões potenciais. 

Destaca-se que este projeto é desenvolvido como produto da disciplina de Machine Learning, integrante do curso de Bacharelado em Ciência e Tecnologia, oferecido pela Universidade ILUM-Escola de Ciência, instituição acadêmica vinculada ao CNPEM (Centro Nacional de Pesquisa em Energia e Materiais). 


Banco de Dados pode ser acessado através do link: https://drive.google.com/file/d/1t3dj_g1M8-sX_Siqc36_rSp_UACnj_bL/view?usp=drive_link

# Lista de Abreviaturas e Siglas

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

A ciência que é utilizada para esta problemática é o Aprendizado de Máquina (Machine Learning), que é um subconjunto da Inteligência Artificial (IA) o qual permite que um sistema aprenda e melhore de forma autônoma usando redes neurais e aprendizado profundo, sem ser programado explicitamente, alimentando-o com grandes quantidades de dados. [2] Dessa forma, seria viável programar um algoritmo que tivesse os dados de solo e clima como entrada (input), e retornasse uma saída (output) da previsão de seca no local analisado. 

Esses dados podem ser coletados de diversas formas possíveis, variando de acordo com sua finalidade e recursos para a pesquisa. Entretanto, algo em comum com todo qualquer tipo de dado é que eles são armazenados em dataset. 

Dataset é um conjunto de dados estruturados em uma tabela, contendo descrições específicas de seus atributos e arquivos significativos para o conjunto. [3] Com o conjunto de dados, é possível extrair informações necessárias para a aplicação/manipulação desejada.

Ao utilizar um dataset que combina dados de solo e clima, pode-se desenvolver modelos de Machine Learning mais robustos e precisos. Esses modelos podem capturar correlações complexas entre as variáveis ambientais e, assim, melhorar a capacidade de prever secas com antecedência. 

A escolha desse tipo de dataset permite uma abordagem multidisciplinar, integrando conhecimentos, sem perder a importância científica proposta pelo trabalho final.

Este dataset não existiria sem a disponibilização pública desses dados oferecidos pela NASA POWER Project (Projeto POWER da NASA) e pelos autores da US Drought Monitor (Monitor de Seca dos EUA). [1] [4] [5].

# Metodologia

Analise exploratória

Ao realizar uma análise detalhada dos dados, constatou-se que o conjunto continha mais de 40 milhões de registros e caracterizava-se como séries temporais, o que apresentava desafios significativos em termos de complexidade e exigência de habilidades, especialmente dentro do escopo da disciplina em questão. Diante dessa situação, decidiu-se trabalhar com uma fração representativa dos dados, optando por utilizar apenas 1/7 (um sétimo) do conjunto. Essa escolha foi fundamentada no fato de que os dados relacionados à seca eram coletados em intervalos de sete dias. Entretanto, é importante destacar que o tratamento de séries temporais não estava contemplado no conteúdo programático da disciplina, mas o dataset estudado permite a liberdade de interpretação fora do campo de séries temporais. Assim, optou-se por conduzir a análise sem levar em consideração essa particularidade, o que reforça a justificativa para a escolha de trabalhar com um subconjunto reduzido de dados. Além disso, observou-se que as informações incluíam registros de diversas localidades, decidiu-se remover as colunas relacionadas à data e localidade.

Multicolinearidade



smoth

# Resultados e Discussões

# Conclusão

# Referências

[1] Predict Droughts using Weather & Soil Data. Disponível em: <https://www.kaggle.com/datasets/cdminix/us-drought-meteorological-data/data>. Acesso em: 11 nov. 2023.

[2] O que é Machine Learning?  |  Google Cloud. Disponível em: <https://cloud.google.com/learn/what-is-machine-learning?hl=pt-br>. Acesso em: 11 nov. 2023.

[3] Dados estruturados de conjunto de dados | Central da Pesquisa Google | Documentação. Disponível em: <https://developers.google.com/search/docs/appearance/structured-data/dataset?hl=pt-br>. Acesso em: 11 nov. 2023.

‌
[4] NASA. NASA POWER | Prediction Of Worldwide Energy Resources. Disponível em: <https://power.larc.nasa.gov/>. Acesso em: 11 nov. 2023.

‌
[5] Contact Us | U.S. Drought Monitor. Disponível em: <https://droughtmonitor.unl.edu/About/ContactUs.aspx>. Acesso em: 11 nov. 2023.

‌
[6] Federal Information Processing Standards. Disponível em: <https://pt.wikipedia.org/wiki/Federal_Information_Processing_Standards>. Acesso em: 11 nov. 2023.

