# Desafio Engenheiro de Dados

1 - Contexto 

Aqui na Projeto22 "conhecimento" é a palavra-chave, disponibilizamos para nossos colaboradores um acervo contendo milhares de documentos dos mais diversos assuntos, a fim de contribuir na busca interminável pelo saber. 

Queremos aumentar ainda mais a nossa disponibilidade de títulos, mas ultimamente notamos que muitos dos nossos colaboradores relatam a enorme dificuldade de encontrar um documento de um determinado assunto, frente ao enorme acervo que disponibilizamos. Na esperança de uma solução fácil que permita a pesquisa de informações através de palavras-chave em nossos documentos, consultamos um de nossos maiores especialistas em Engenharia de Dados ...Tobias "The Guy"! 

Tobias, com o objetivo de resolver o problema da forma mais simples e eficiente, decidiu utilizar uma representação vetorial para nossos documentos. Mecanismos de pesquisa utilizam diversos tipos de representações de documentos, uma delas é a representação vetorial. Esta representação permite o uso direto de ferramentas matemáticas como distância, similaridade e redução de dimensão. 

Só que surgiu um pequeno problema, devido ao enorme backlog de demandas, Tobias está com falta de disponibilidade para atuar na solução do nosso problema :( 
Aí que você entra, jovem entusiasta do saber, pedimos sua ajuda para implementar este grande desafio, para que a busca incessante pelo saber não acabe!

Nosso desafio não se resume a ferramentas matemáticas, mas sim sobre a construção de um índice reverso que acelere os cálculos. Muitas vezes os cálculos necessários são baseados em produto escalar que acabam consumindo muita memória e CPU do computador, tendo um índice reverso simplifica em muito os cálculos.

Nós precisamos que você escreva uma implementação eficiente de um índice reverso, que indexe uma quantidade grande de documentos.



2 - Algoritmo
2.1 Documentos

Nós temos uma coleção de N documentos. Em nosso caso, nós temos 1 arquivo por documento e o nome do arquivo é simplesmente o número do índice do documento como mostrado na figura 1.
 

2.2 Dicionário

Nós queremos um dicionário que realize um “match” de cada palavra contida nos documentos com um identificador único “word_id”, conforme figura 2.

 

2.2.1 Índice reverso

Usando ambos o conjunto de dados e dicionário, nós conseguimos construir um índice reverso que dá, para cada palavra, a lista de documentos em que a palavra está contida, veja figura 3.

 
  
Nós queremos uma solução que funcione para um grande conjunto de dados. Nosso algoritmo tem que ser capaz de rodar em um sistema distribuído, de forma que não fiquemos limitados a quantidade de disco, memória e CPU de uma única máquina.
Estes são os 4 passos do algoritmo:
•	Ler os documentos e recuperar cada par (wordId, documentId)
•	Ordenar cada par por worldId e documentId
•	Para cada worldId, agrupar os pares, para ter a lista de documentos que contém a palavra
•	Mesclar os resultados intermediários para ter o índice reverso final  




Veja figura 4, etapas do algoritmo.
 
 
Atenção: o índice deve ser ordenado pelos identificadores das palavras e para cada identificador de palavra, ordenar a sua respectiva lista de identificadores de documentos. 
Caso seja de interesse, vide “Blocked sort-based indexing”

3 – Questionamentos
Você encontrará o conjunto de dados de documentos no diretório dataset do repositório no GitHub

1 – Implemente um Job para construir o dicionário. Cada linha do arquivo de saída deverá ser a palavra seguida de seu identificador (world_id). Nos documentos contidos no dataset as palavras estão separadas por um ou mais espaços.
2 – Implemente um ou mais Jobs para construir o índice reverso

Você deve usar Hadoop ou Spark [ou ambos (*pontos a mais)] para estes Jobs e a linguagem que preferir (sugestões ordenadas por nossa preferência: Scala, Java, Python)

