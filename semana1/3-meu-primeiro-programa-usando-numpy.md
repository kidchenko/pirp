# Meu primeiro programa de processamento de imagens usando Numpy

O Numpy adiciona o tipo `ndarray` ao Python, que é utilizado para representar uma imagem no estilo matricial.

A programação matricial, é um estilo de programação que ajuda a reutilizar operações e manipulações matriciais conhecidas, aumenta a clareza do código, diminuindo o número de linhas e favore a eficiência de execução visto a disponibilidade cada vez maior de hardware que processsa operações vetorias.

### Representação, Leitura  e Visualização de Imagens

Uma imagem digital pode ser representada por uma matriz bidimensional, onde os seus elementos são chamados de pixels, dessa forma todas as operações disponíveis para processamento matricial podem ser utilizados com processamento de imagens.

### Imagem como matriz e Numpy

No Numpy uma imagem é definida pelo seu cabeçalho (tabalho da matriz e tipo de pixel) e pelo seu corpo (os pixels em si).

O tamanho da matriz é caracterizado pelas suas dimensões: vertical e horizontal. A dimensão vertical é definida pelo número de linhas (rows) ou altura (heigth) H e a dimensão horizontal é definida pelo número de colunas (cols) ou largura (width) W. No Numpy, as dimensões são armazendas no **shape** da matriz como uma tupla (H, W)

Os pixels de uma imagem podem ser de vários tipos
- Image binária: tem apenas dois valores possíveis, muitas vezes atribuídos a preto e branco
- Imagem em nível de cinza: tem valores inteiros positivos, muitas vezes, de 0 a um valor máximo.

É possível ter pixels com valores negativos, com números reais, e até mesmo pixels com valores comlexos. Um exemplo de uma imagem com valores de pixel negativos são imagens térmicas com temperaturas negativas. As imagens com pixels que são números reais podem ser encontradas nas imagens que representam uma onda senóide com valores que variam de -1 a +1. As imagens com valores de pixel complexos podem ser encontrados em algumas transformações da imagem com a Transformada Discreta de Fourier.

Imagens possuem centenas de milhões de pixels, escolher a menor representação do pixel faz com que a imagem não seja muito grande otimizando espaço processamento.

No Numpy o tipo de pixel é armazenado no dtype que pode assumir vários tipos. Os quatro tipos mais usados são:

| **dtype**       | valores           |
| :-------------  | :-------------    |
| bool            | True ou False     |
| uint8           | 0 a 255           |
| int             | 64bits com sinal  |
| float           | ponto flutuante   |


No Numpy uma imagem em RGB é representada como três imagens armazenadas na dimensão profundiade da matriz. Nesse caso a matriz tem 3 dimensões e seu shape tem formato de (3, H, W)


### Visualizando numéricamente uma imagem

Se a imagem tiver muitos pixels, a impressão de todos os pixels é feita de uma forma especial, visto que se fossem imprimdos todos os pixels o resultado não seria muito satisfatório. Nessa caso, quando a imagem (matriz) é muito grande o Numpy imprime apenas os pixels dos quatro cantos da imagem.

### Visualizando numericamente uma pequena região de interesse da imagem

Para imprimir uma parte da imagem você usa o conceito de fatiamento de arrays em python. Por exemplo se você quiser uma região de 7 linas e 10 colutas você usa:
```python
g = f[:7, :10]
```

### Dicas

Sabe-se que a dimensao da imagem (matriz) é sua largura e altura. Baseado nisso você já sabe os limites da sua matriz. A origem é 0,0. E para acessar cada elemento vc usa: `f[h, w]`. Para percorrer toda a matriz, use dois `for` encadeados.

Continua em: http://adessowiki.fee.unicamp.br/adesso-1/wiki/pirp/activity_kiide_1_3/view/ & http://adessowiki.fee.unicamp.br/adesso-1/wiki/master/tutorial_img_ds/view/
