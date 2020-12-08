# Projeto - Gerenciador de Memória - SIN351

### Memory Manager
>**Status:** Em andamento :shipit:

>**Descrição:** Segundo projeto proposto pelo professor Rodrigo Moreira da disciplina de Sistemas Operacionais - SIN351 da **Universidade Federal de Viçosa - Campus Rio Paranaíba (UFV-CRP)**. 

### Developed by:
* Jhonatha Cordeiro Gomes - 5984
  * https://github.com/jhonathadev
* Viviane Renizia Mendes Silva - 5209
  * https://github.com/vivianerenizia

### Seções:

:small_blue_diamond:[*Objetivos*](#Objetivos)

:small_blue_diamond:[*Funcionamento*](#Funcionamento)

:small_blue_diamond:[*Comparação*](#Comparação)

:small_blue_diamond:[*Contato*](#Contato)

### Objetivos:
* Introduzir os conceitos de Gerenciamento de Memória;
* Familiarizar o estudante com as técnicas de subistituição de Páginas dos Sistemas Operacionais Modernos;
* Aprimorar as capacidades de programação em Linguagem C.

### Funcionamento:
Neste projeto foi implementado em linguagem C algoritmo de subistituição de páginas (Conteúdo de Memória Virtual) e comparado o desempenho do Algoritmo implementado com o Random (Aleatório) disponibilizado pelo professor. Posteriormente foi produzido um relatório técnico explicando as principais funcionalidades do código e do algoritmo de
subistituição de páginas escolhido. Ao final da execução do programa, é exibido a quantidade de falta de páginas para cada algoritmo: o desenvolvido pelo aluno e o Random. 


* Passo 01 - Compilando o código
~~~C
$ gcc -Wall vmm.c -o vmm
~~~
* Passo 02 - Execução 
   * 3 algritmos podem ser executados: FIFO, Second Chance e Random.
   * Para execução, é preciso utilizar 3 parâmetros como demonstrado abaixo: 
~~~C
$ ./vmm fifo 10 < anomaly.dat
~~~
~~~C
$ ./vmm second_chance 10 < anomaly.dat
~~~
~~~C
$ ./vmm random 10 < anomaly.dat
~~~

* Exemplos:
Exemplos de compilação e execução no terminal Linux serão inseridos aqui em formato de imagens posteriormente.

### Comparação

Uma tabela com várias execuções dos algoritmos afim de comparação de desempenho, contendo tbm uma média será inserida aqui posteriormnte.

### Contato:
* Jhonatha Cordeiro Gomes 
  * https://www.linkedin.com/in/jhonathacordeiro/
* Viviane Renizia Mendes Silva
  * https://www.linkedin.com/in/vivianerenizia/
