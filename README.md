# Projeto - Gerenciador de Memória - SIN351

### Memory Manager
>*Status:* Concluído :white_check_mark: :shipit:

>*Descrição:* Segundo projeto proposto pelo professor Rodrigo Moreira na disciplina de Sistemas Operacionais - SIN351 da *Universidade Federal de Viçosa - Campus Rio Paranaíba (UFV-CRP)*. 

### Developed by:
* Jhonatha Cordeiro Gomes - 5984
  * https://github.com/jhonathadev
* Viviane Renizia Mendes Silva - 5209
  * https://github.com/vivianerenizia

### Seções:

:small_blue_diamond:[Objetivos](#Objetivos)

:small_blue_diamond:[Funcionamento](#Funcionamento)

:small_blue_diamond:[FIFO](#FIFO)

:small_blue_diamond:[Comparação](#Comparação)

:small_blue_diamond:[Problemas e bugs](#Problemas)

:small_blue_diamond:[Contato](#Contato)

### Objetivos:
* Introduzir os conceitos de Gerenciamento de Memória;
* Familiarizar o estudante com as técnicas de subistituição de Páginas dos Sistemas Operacionais Modernos;
* Aprimorar as capacidades de programação em Linguagem C.

### Funcionamento:
Neste projeto foi implementado em linguagem C um algoritmo de subistituição de páginas (Conteúdo de Memória Virtual) e comparado o desempenho do Algoritmo implementado com o Random (Aleatório) disponibilizado pelo professor. Posteriormente produzimos um relatório técnico explicando as principais funcionalidades do código e do algoritmo de
subistituição de páginas escolhido. Ao final da execução do programa, é exibido a quantidade de falta de páginas para cada algoritmo: o desenvolvido pelo aluno e o Random. 


* Passo 01 - Compilando o código
~~~C
gcc -Wall vmm.c -o vmm
~~~

<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/compilando.png" height="400" width="700">

* Passo 02 - Execução 
   * 2 algoritmos podem ser executados: FIFO e Random.
   * Para execução, é preciso utilizar 3 parâmetros como demonstrado abaixo: 
~~~C
./vmm fifo 10 < anomaly.dat
~~~
<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/fifocomando.png" height="400" width="700">

~~~C
./vmm random 10 < anomaly.dat
~~~
<img src="https://github.com/vivianerenizia/MemoryManagerSIN351/blob/master/imgs/randomcomando.png" height="400" width="700">

### FIFO:

* O conceito FIFO (First In, First Out) é bem simples: substitui a página que esteve na memória por mais tempo.

* Na implementação, basta manter uma fila de todas as páginas na memória. Elas são adicionadas ao final da fila quando lidas para a memória. A página que sofre swap para o disco é sempre escolhida da frente da fila.

> Na nossa implementação, a função retorna o índice da página que será substituída. 

* O fifo_frm indica qual a mais velha na memória física, ou seja, qual será substituída, como explicado anteriormente.
   * Dessa forma, percorremos a tabela de página utilizando um for (i=0 até o número de páginas) e verificamos se a página de índice i tem o mesmo valor que o fifo_frm e assim podemos retornar qual deve ser substituída. Veja abaixo:
   
~~~C
int fifo(int8_t** page_table, int num_pages, int prev_page, int fifo_frm, int num_frames, int clock){ 
	int i;
	for (i=0;i<num_pages;i++){
		if(page_table[i][PT_FRAMEID]==fifo_frm){
			return i; 
		}
	}
    return -1;
}
~~~

> É possível notar que para a nossa implementação não utilizamos **todos** os parâmetros definidos inicialmente no esqueleto.

### Comparação:

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
   * O FIFO sempre dá o mesmo resultado;
   * O RANDOM, por ser aleatório, traz resultados diversos;
   * O algoritmo RANDOM possui performance duvidosa já que depende da aleatoriedade, pode ser bom ou ruim;
   * As médias de Page Fault foram próximas uma da outra;
   * Ambos os algoritmos tem desempenho duvidoso em relação aos outros algoritmos de troca de página, existem melhores.

### Problemas e bugs:

* Um ponto importante a se destacar é a complexidade do esqueleto disponibilizado. Código um pouco extenso, complexo e com poucos comentários.
   * Devido a isso, uma grande parcela do tempo disponibilizado para confecção do projeto, foi gasto em execuções, prints e testes de mesa do código.

* A descrição do projeto também nos levou a entender que algo mais, além da implementação do algoritmo escolhido, deveria ser feito.
   * Porém, provavelmente foi apenas uma interpretação equivocada da equipe.

* Assert, fifo_frm e to_free
   * Não conseguimos solucionar um bug no projeto. Nosso algoritmo retorna corretamente o número de page faults, mas printando as variáveis to_free e fifo_frm é possível perceber que elas não estão apontando o mesmo endereço, possuem valores diferentes. Com outras implementações testadas retornava um bug de mapeamento e não obtinhamos o resultado esperado. 
       > * Em conclusão, retornamos o resultado correto, porém, a página retirada da memória pode não ser a página correta. Não conseguimos "driblar" o assert.
       
### Contato:
* Jhonatha Cordeiro Gomes 
  * https://www.linkedin.com/in/jhonathacordeiro/
* Viviane Renizia Mendes Silva
  * https://www.linkedin.com/in/vivianerenizia/
