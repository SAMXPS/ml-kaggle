 # Inteligência Artificial
 
Escreva um programa que retorne as raizes de uma equação de segundo grau. Escreva um programa que calcula a menor rota entre dois pontos. Escreva um programa que auxilie uma empresa de transporte a minimizar o tempo de entrega e os gastos com combustível. Escreva um programa que reconheça pessoas pelo rosto ou pela fala. Escreva um programa para dirigir um carro de forma autônoma. Escreva um programa para idenitificar buracos negros. Escreva um programa que controle os jogadores de um time de futebol de robôs. Escreva um programa que jogue Dota 2 e seja melhor que o melhor jogador humano. 

Qual estrutura de dados esses programas utilizam? Qual a complexidade desses algoritmos? O que eles tem de similares? O que eles tem de diferentes? Existe mais de um algoritmo que resolve o mesmo problema? Você consegue pensar em pelo menos uma solução para cada problema? O ser humano consegue resolver todos esses problemas? Como o ser humano consegue resolver todos esses problemas? Responder essas perguntas pode ser relativamente difícil, portanto vamos assumir algumas premissas antes de começar. A primeira dela é que o ser humano consegue realizar boa parte das tarefas diárias porque ele é bom em reconhecer padrões. 

Padrões no discionário Michaelis on-line é "aquilo que tem forma, tamanho, dimensões mais comuns em sua categoria ou em seu gênero; modelo, tipo". Um médico consegue, com um conjunto de sintomas e de resultados de exames clínicos, diagnosticar se um paciente esta com algum problema cardíaco. Para isso ele utiliza o conhecimento adiquirido durante os 6 anos de formação e sua experiencia durante o exercício da profissão. É provavel que somente utilizando o conhecimento adiquirido nos livros o médico fosse capaz de diagnosticar. Mas será que a experiência também não é importante? 

Nos primórdios da Inteligência Artificial (IA), por volta de 1970, esses conhecimentos eram extraidos dos especialistas e regras lógicas eram construídas de forma a possibilitar a automatização das tarefas, sejam elas de diagnósticos de doenças, predizer se o banco deveria ou não emprestar dinheiro para uma pessoa e etc. Ou seja, o processo de aquisição de conhecimento normalmente envolvia entrevistas e a cooperação por parte do especialsta resultado em uma tarefa completamente subjetiva.

Nas últimas décadas, a expansão da coleta de dados, o crescimento dos volumes de dados coletados, a necessidade de processamento desses dados e extração de conhecimento de forma automática, surgiu a necessidade de automatizar a extração de conhecimento. Ou seja, surgiu a necessidade de ferramentas que fossem capazes de criar por sí próprias, a partir de experiencia passada, uma hipótese ou função capaz de resolver um determinado problema. Uma hipótese ou função pode ser um regra ou conjunto de regras que descrevem o comportamento de um problema em relação a algum comportamento esperado. Esse processo de construção/indução de uma hipótese ou função recebe o nome de Aprendizado de Máquina (AM).

Uma das definições classicas de AM foi dada por Mitchell em 1997 no livro *Machine Learning*: "Aprendizado de Máquina é a capacidade de melhorar o desempenho na realização de uma tarefa por meio da experiência". Ou seja, esperamos um comportamento inteligente quando temos a capacidade de memorizar, observar e aprender fatos por meio de práticas de organização do conhecimento em novas representações.

Imagine uma base de dados que contém exemplos de equações de segundo grau 
<img src="https://render.githubusercontent.com/render/math?math=ax^2 %2B by %2B+ c = 0"> e suas raizes 
<img src="https://render.githubusercontent.com/render/math?math=r_1"> e <img src="https://render.githubusercontent.com/render/math?math=r_2">. Nessa base de dados, cada linha representa uma amostra/dado/objeto e cada coluna/variável/atributo uma característica relacionada a essa amostra. Perceba que as três primeiras colunas são os índices das equações de segundo grau e as duas últimas colunas as raizes.

| a | b  | c   | r1  | r2  |
|---|----|-----|-----|-----|
| 1 | -5 | 6   | 3   | 2   |
| 4 | -4 | 1   | 1/2 | 1/2 |
| 1 | 2  | -15 | 3   | -5  |

Naturalmente podemos inferir as raizes porque já conhecemos a [Fórmula de Bhaskara](https://pt.wikipedia.org/wiki/Equa%C3%A7%C3%A3o_quadr%C3%A1tica) que resolve as equações de segundo grau e retorna os valores das raizes. Para chegar nessa equação, Bhaskara utilizou o método de completamento de quadrados. No entanto, imagina que ela é desconhecida da humanidade e Bhaskara nunca nasceu.  Qual seria a hipótese ou função que retornaria os valores das raizes? Uma alternativa seria utilizar o aprendizado indutivo.

Indução no discionário Michaels significa "forma de raciocínio que leva à conclusão de um certo caso com base na observação da regularidade de uma ocorrência". Ou seja, podemos entender que os algoritmos de Aprendizado de Máquina aprendem por meio da experiência, ou seja, aprendizado indutivo. Quando um algoritmo de Aprendizado de Máquina esta aprendendo a partir de um conjunto de dados, ele esta procurando uma hipótese, no espaço de possíveis hipóteses, capaz de descrever as relações entre objetos e que melhor se ajuste aos dados.

## Indução da hipótese ou função

O que se deseja é construir uma hipótese capaz de predizer os valores das raizes de uma determina equação de segundo grau antes nunca vista. Assim, uma vez induzida uma hipótese, é esperado que ela também seja valida para outras amostras do mesmo domínio mas que não fazem do conjunto de treinamento. A essa capacidade da hipótese continuar valendo para outros objetos dá-se o nome de capacidade de generalização da hipótese. 

O objetivo de um algoritmo de AM utilizado nessa tarefa é aprender, a partir de um subconjunto dos dados, um modelo, hipótese ou função capaz de relacionar os valores dos atributos de entrada de um objeto ao valor do seu atributo de saída. Além disso é importante que os algoritmos de AM sejam capazes de lidar com dados imperfeitos. Muitos conjuntos de dados apresentam algum tipo de imperfeição como presença de ruídos, dados ausentes e redundantes.

Quando uma hipótese apresenta baixa capacidade de generalização, pode ser que ela esteja superajustada aos dados (overfitting). Também podemos dizer que a hipótese memorizou os dados. Quando a hipótese aprensenta baixa capacidade de generalização inclusive no conjunto de treianmento, dizemos que ela subajustou aos dados (underfitting). Essa condição pode acontecer quando o conjunto de treinamento é pequeno e pouco representativo ou o algoritmo utilizado para construir a hipótese é muito simples. A Figura a seguir apresenta exemplos de *overfitting*, *underfitting* e um hipótese ideal.

![](over_under.png) *Exemplo de hipóteses para uma base de dados. Adaptado de https://medium.com/greyatom/what-is-underfitting-and-overfitting-in-machine-learning-and-how-to-deal-with-it-6803a989c76*


## Viés dos algoritmos

## Classificação do Aprendizado





