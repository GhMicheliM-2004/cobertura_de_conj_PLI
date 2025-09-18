# Problema de Máxima Cobertura como variante do Problema de Cobertura de Conjuntos em PLI
Gustavo Henrique Sargi Michelim¹, Henrique Rosa de Araújo²

Departamento de Informática – Universidade Estadual de Maringá (UEM)
Avenida Colombo, 5790 – Bloco C56 – 87020-900 – Maringá – PR – Brasil

Departamento de Informática
Universidade Estadual de Maringá (UEM) - Maringá, PR - Brasil

ra128968@uem.br, ra107800@uem.br

Resumo. Este trabalho apresenta uma abordagem baseada em Programação Linear Inteira (PLI) para resolver uma variante do Problema de Máxima Cobertura (MCP). A formulação utilizada foi inspirada na modelagem proposta por Prata (2012), na qual busca-se selecionar um número limitado de colunas de uma matriz binária de forma a minimizar o número de linhas não cobertas. Ao contrário do estudo de referência, que emprega uma heurística de Enxame de Partículas (PSO binário), a solução aqui apresentada utiliza um método exato, baseado em PLI. Os experimentos realizados mostram que essa abordagem é capaz de encontrar soluções ótimas de forma eficiente para as instâncias analisadas..

Introdução
O Problema de Cobertura de Conjuntos (PCC) é um problema clássico de otimização combinatória, NP-difícil, cuja aplicação abrange diversas áreas como logística, localização de instalações e alocação de recursos. Este estudo trabalha com uma variante minimizadora, semelhante ao Problema das p-Medianas, conforme apresentado por Prata (2012). Enquanto o artigo referência explora a eficiência de um PSO binário, e este artigo explora uma solução em PLI a para a variante proposta.
Conforme proposta deste trabalho, a variante utilizada do Problema de Cobertura de Conjuntos é o Problema de Máxima Cobertura (Maximum Covering Problem – MCP).

Definição Formal
O Problema de Cobertura de Conjuntos (Set Covering Problem – SCP) é um problema clássico de otimização combinatória, pertencente à classe NP-difícil, com aplicações em áreas como logística, localização de instalações e alocação de recursos. Neste trabalho, é abordada uma variante minimizadora conhecida como Problema de Máxima Cobertura (Maximum Covering Problem - MCP).
A modelagem adotada neste estudo é baseada na proposta de Prata, que visa selecionar um subconjunto limitado de colunas de uma matriz binária de modo a minimizar o número de linhas não cobertas. Entretanto, enquanto o autor original emprega uma heurística baseada em Enxame de Partículas (PSO binário), este trabalho adota uma abordagem exata por meio da Programação Linear Inteira (PLI), buscando avaliar sua efetividade na resolução do problema modelado.


Próximas seções
A Seção 4 formaliza o problema abordado e apresenta seu modelo de Programação Linear Inteira. A Seção 5 descreve a implementação computacional, o ambiente de testes, as instâncias utilizadas e os resultados experimentais. A Seção 5 também discute os resultados obtidos. A Seção 6 apresenta as considerações finais. Por fim, a seção 7, apresenta as referências utilizadas e encerram o artigo.

Modelo de Minimização do número de conjuntos não cobertos
Neste trabalho, adota-se a formulação proposta por Prata (2012) para uma variante do Problema de Máxima Cobertura. A modelagem considera uma matriz binária A∈{0,1}m×n, onde cada linha representa um elemento a ser coberto e cada coluna representa um subconjunto disponível. A entrada aij​=1 indica que o elemento i pertence ao subconjunto j.

Define-se:
xj​∈{0,1}: variável binária que indica se a coluna j (subconjunto) foi selecionada;
yi∈{0,1}: variável binária que indica se a linha i (elemento) não foi coberta;
d: número máximo de subconjuntos que podem ser escolhidos;
aij: elemento de A, que indica se o elemento i pertence ao subconjunto j.

A formulação matemática é dada por:

Fonte: Um algoritmo enxame de partículas para uma variante do problema de máxima cobertura - Prata (2012)

O Problema de Máxima Cobertura é um problema de variáveis de caráter binário, onde se a variável yi=1, não é coberta na solução, e caso contrário (yi=0) significa que é coberta pela solução. A variável xj​, caso seja xj​=1, significa que a coluna faz parte da solução, e caso contrário (xj​=0) significa que a coluna não faz parte da solução. O objetivo é minimizar o número de elementos não cobertos (yi=1), dado um limite superior d sobre a quantidade de subconjuntos (colunas) que podem ser selecionados, a restrição 2 garante esse limite. A restrição 3 assegura que cada linha da matriz seja coberta por ao menos uma das colunas selecionadas, ou então será considerada não coberta, ou seja, caso a i-ésima linha da matriz não possa ser coberta, receberá o valor b-inário yi=1. As restrições 4 e 5 apenas realizam a demonstração do caráter binário das variáveis.
