# Projeto - Gerenciador de Memória - SIN351

### Memory Manager
>*Status:* Em andamento :shipit:

>*Descrição:* Segundo projeto proposto pelo professor Rodrigo Moreira da disciplina de Sistemas Operacionais - SIN351 da *Universidade Federal de Viçosa - Campus Rio Paranaíba (UFV-CRP)*. 

### Developed by:
* Jhonatha Cordeiro Gomes - 5984
  * https://github.com/jhonathadev
* Viviane Renizia Mendes Silva - 5209
  * https://github.com/vivianerenizia

### Seções:

:small_blue_diamond:[Objetivos](#Objetivos)

:small_blue_diamond:[Funcionamento](#Funcionamento)

:small_blue_diamond:[Comparação](#Comparação)

:small_blue_diamond:[Contato](#Contato)

### Objetivos:
* Introduzir os conceitos de Gerenciamento de Memória;
* Familiarizar o estudante com as técnicas de subistituição de Páginas dos Sistemas Operacionais Modernos;
* Aprimorar as capacidades de programação em Linguagem C.

### Funcionamento:
Neste projeto foi implementado em linguagem C algoritmo de subistituição de páginas (Conteúdo de Memória Virtual) e comparado o desempenho do Algoritmo implementado com o Random (Aleatório) disponibilizado pelo professor. Posteriormente foi produzido um relatório técnico explicando as principais funcionalidades do código e do algoritmo de
subistituição de páginas escolhido. Ao final da execução do programa, é exibido a quantidade de falta de páginas para cada algoritmo: o desenvolvido pelo aluno e o Random. 


* Passo 01 - Compilando o código
~~~C
gcc -Wall vmm.c -o vmm
~~~

<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/compilando.png" height="400" width="700">

* Passo 02 - Execução 
   * 3 algritmos podem ser executados: FIFO, Second Chance e Random.
   * Para execução, é preciso utilizar 3 parâmetros como demonstrado abaixo: 
~~~C
./vmm fifo 10 < anomaly.dat
~~~
<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/fifocomando.png" height="400" width="700">

~~~C
./vmm random 10 < anomaly.dat
~~~
<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/randomcomando.png" height="400" width="700">

### Comparação

EXECUÇÃO |FIFO    |RANDOM  |
:-------:|:------:|:------:| 
1        |9       |10      |
2        |9       |8       |
3        |9       |9       |
4        |9       |8       |
5        |9       |7       |
6        |9       |8       |
7        |9       |9       | 
8        |9       |7       |
9        |9       |10      |
10       |9       |9       |
11       |9       |8       |
12       |9       |8       |
13       |9       |8       |
14       |9       |9       |
15       |9       |10      |
***MÉDIA***|*9*   |*8,5*   |

* A tabela acima traz o resultado de 15 execuções de FIFO e RANDOM. Assim, pode-se observar:
   * O FIFO sempre dá o mesmo resultado
   * O RANDOM, por ser aleatório, traz resultados diversos;
   * O algoritmo RANDOM possue performance duvidosa já que depende da aleatoriedade;
   * As médias de Page Fault foram próximas uma da outra;
   * Ambos os algoritmos tem desempenho duvidoso em relação aos outros algoritmos de troca de página, existem melhores.

### Contato:
* Jhonatha Cordeiro Gomes 
  * https://www.linkedin.com/in/jhonathacordeiro/
* Viviane Renizia Mendes Silva
  * https://www.linkedin.com/in/vivianerenizia/
