# Computação Gráfica

## Cor

### O que é cor?
- Cor é uma sensação produzida no cérebro pela luz que chega aos olhos.
- Permite:
  - Impressionar
  - Expressar
  - Construir

### Aplicações
- TV, cinema, impressão
- Medicina
- Análise de dados
- Segurança
- Jogos

### Conceito de Cor
- Cor é a manifestação perceptual da luz.
- A luz é um sinal eletromagnético.
- Percebemos milhões de cores diferentes, mas só na presença de luz.

### Paradigma dos Quatro Universos

1. **Cores no Universo Físico**
   - A cor é produzida por radiação eletromagnética que possui comprimentos de onda dentro do espectro visível. As cores que percebemos são resultado da interação da luz com os objetos ao nosso redor.

2. **Modelos Matemáticos**
   - São descrições matemáticas usadas para representar a cor, baseadas em leis da física e matemática. Esses modelos nos permitem compreender como a luz e a cor são interpretadas pelos dispositivos e sistemas gráficos.

3. **Representação da Cor**
   - Trata-se da forma como a cor é representada digitalmente, como em sistemas de cores como **RGB**, onde as cores são codificadas por combinações de valores de vermelho, verde e azul. Cada cor percebida pode ser descrita por diferentes combinações desses valores.

4. **Especificação da Cor**
   - Envolve a determinação exata da cor em um contexto específico, com base em padrões e coordenadas de cor em espaços como RGB, CMYK, ou CIE. Isso permite que a cor seja replicada fielmente em diferentes dispositivos e contextos.


### Espaço Espectral de Cor
- A decomposição da energia radiante em função dos comprimentos de onda chama-se distribuição espectral.
- **Espectrofotômetro**: Dispositivo para obter a distribuição espectral de uma cor.
- **Cor Espectral Pura**: Possui energia em um único comprimento de onda.
- A soma de duas distribuições espectrais resulta em uma combinação aditiva de cores.

### Representação de Cor
- O espaço espectral possui dimensão infinita, mas buscamos uma representação finita, associada a sistemas físicos.
- **Sistema de Young-Helmholtz**: O olho humano amostra três pontos distintos do espectro visível:
  - Vermelho (baixas frequências)
  - Azul (altas frequências)
  - Verde (médias frequências)

### Reconstrução Perceptual
- O objetivo não é reproduzir exatamente a mesma cor, mas sim uma cor perceptualmente igual à original.
- **Metamerismo**: Duas cores com distribuições espectrais diferentes, mas perceptualmente idênticas.

### Sistemas Físicos de Cor
- Realizam operações de representação e reconstrução de cor.
  - **Sistemas Receptores**: Exemplo: olho humano.
  - **Sistemas Emissores**: Exemplo: televisão.

### Sistema de Cores
- Modelo que explica o comportamento das cores em um contexto específico.
- **Espaços de Cor**: RGB, HSV, etc.

### Sistema Padrão CIE-RGB
- Adotado pelo CIE em 1931.
- As cores primárias são R (vermelho), G (verde) e B (azul).

### Luminância e Crominância
- **Modelo de Hering**: Define três canais para percepção de cores:
  - Luminância (brilho)
  - Vermelho-verde
  - Azul-amarelo

### Luminância e Valor
- **Luminância**: Brilho.
- **Matiz**: Tonalidade.
- **Saturação**: Quantidade de cor branca.

### Cores Complementares
- Cada cor tem uma cor complementar cuja soma resulta em branco (luz acromática).
  - Vermelho - Ciano
  - Verde - Magenta
  - Azul - Amarelo
  - RGB - CMY

### Sistemas dos Dispositivos Gráficos
- **Reconstrução de cor** em monitores é determinada pelo tipo de fósforo utilizado.
- **Modelo HSV**: Hue (cor), Saturation (quantidade de cinza), Value (brilho).

## Introdução à OpenGL


### O que é OpenGL?
- **OpenGL (Open Graphical Library)**: API específica para desenhos vetoriais em interfaces gráficas.
- É independente de dispositivos e amplamente utilizada para modelagem 2D e 3D.
- Possui alta performance em ambientes com poucos polígonos e oferece cerca de 250 comandos básicos.

### Por que OpenGL?
- **Portabilidade e Desempenho**: OpenGL é rápida e dá suporte para animação, iluminação, mapeamento de textura e transparência.
- Fornece um conjunto de primitivas gráficas como pontos, linhas e polígonos.
- Também possibilita a aplicação de transformações geométricas como rotações, translações e escalas.

### Aplicações
- OpenGL é utilizada em diversas áreas, como:
  - Jogos
  - Imagens médicas
  - Programas de modelagem para efeitos especiais em televisão ou cinema

### Bibliotecas Auxiliares
- **GLU (OpenGL Utility Library)**: Oferece rotinas de alto nível para tarefas mais complexas que utilizam as funções básicas da OpenGL.
- **GLUT (OpenGL Utility Toolkit)**: Biblioteca independente de plataforma que fornece elementos de interface com o usuário, como menus pop-up e suporte para dispositivos como joysticks.

### Funções OpenGL
- As funções primitivas de OpenGL são responsáveis por operações gráficas como especificar vértices e definir cores para objetos gráficos. Todas seguem uma convenção de nomenclatura que facilita a utilização.

### Máquina de Estados
- OpenGL funciona como uma **máquina de estados**, onde a aplicação pode alterar modos, como por exemplo, definir a cor atual dos objetos a serem desenhados.
- Estados como iluminação podem ser habilitados ou desabilitados conforme a necessidade do programa.




## Formato dos Dados Gráficos e Resolução

### Classificação dos Dados Gráficos
Em computação gráfica, uma imagem pode ser classificada de duas formas distintas:
- **Vetorial**: Baseada em vetores matemáticos.
- **Raster**: Baseada na descrição da cor de cada pixel.

#### Imagens Raster
- Imagens raster (ou bitmap) descrevem cada pixel de uma imagem.
- Utilizadas frequentemente em fotografia, pois envolvem cálculos complexos, como interpolação e álgebra matricial.
- Cada pixel contém informações para os três canais de cor (RGB).
- Imagens raster possuem boa qualidade de visualização, mas ocupam muito espaço físico.

#### Imagens Vetoriais
- Baseadas em descrições geométricas de formas, como retas, curvas e polígonos.
- Utilizam vetores matemáticos, o que as torna leves e escaláveis sem perda de qualidade.
- Curvas de Bézier são usadas para manipular pontos em desenhos vetoriais.
- Vantagem: possibilidade de isolar objetos e tratá-los independentemente.

### Tipos de Arquivos Gráficos

#### BMP (Bitmap “puro”)
- Arquivo grande, sem compressão, mas compatível com quase todos os programas.
- Não tem limite de cores, mas é evitado na internet devido ao grande tamanho.

#### GIF (Graphic Interchange File)
- Limite de 256 cores, com versões que suportam transparência (GIF 89a).
- Compactação sem perda de qualidade, ideal para imagens simples e animações.
- Utilizado amplamente na internet.

#### PNG (Portable Network Graphics)
- Criado como alternativa ao GIF, suporta até 16,8 milhões de cores (24 bits).
- Compressão eficiente sem perda de qualidade, com suporte a transparência.

#### TIF (Tagged Image File)
- Formato muito usado na indústria gráfica, mas pouco utilizado na internet.
- Compacta sem perder qualidade e é recomendável ativar a compressão LZW.

#### JPG (ou JPEG - Joint Photographics Experts Group)
- Utiliza compressão com perda de qualidade, ideal para reduzir o tamanho de arquivos.
- Adequado para envio de arquivos via internet, mas não para edições contínuas devido à perda cumulativa de qualidade.
- JPEG 2000 (JP2) é uma versão aprimorada, com suporte a compressão sem perda de qualidade.

#### PSD (Photoshop)
- Formato utilizado pelo Adobe Photoshop, suporta layers (camadas) de imagens.
- Ideal para edição, mas não recomendado para impressão, onde TIF, JPG ou PDF são preferíveis.

#### WMF (Windows Meta Files)
- Padrão gráfico da Microsoft, usado em aplicativos como os cliparts do Office.

#### PS e EPS (PostScript e Encapsulated PostScript)
- Utilizado por impressoras PostScript e aplicativos gráficos, armazena figuras e informações sobre fontes.

#### PDF (Portable Document Format)
- Evolução do EPS, é compacto, estável e independente de sistema operacional.
- Amplamente usado para envio de arquivos eletrônicos no mercado gráfico.

### Qualidade da Imagem
- A qualidade da imagem depende da resolução (número de pixels) e da quantidade de bits usados para descrever as cores.
- Exemplos de classificação:
  - 1 bit/pixel: 2 cores.
  - 4 bits/pixel: 16 cores.
  - 8 bits/pixel: 256 cores.
  - 24 bits/pixel: até 16 milhões de cores.
  - 32 bits/pixel: até 4 bilhões de cores.

## Dispositivos para Imagens
Características a serem consideradas em dispositivos gráficos:
- Trabalha com cores ou em escala de cinza.
- Número de bits por pixel (ex.: 1, 4, 8, 16, 24, 32).
- Paleta de cores ou não.
- Resolução (pixels por polegada ou linhas horizontais).
- Modelo de cor: aditivo ou subtrativo.

### Exemplo de Dispositivos

#### Monitor de Computador CRT
- Colorido.
- 4, 8, 16 ou 24 bits por pixel.
- Pode ter paleta de cores (4 bits ou 8 bits).
- Resoluções comuns: 640x480, 800x600, 1024x768.

#### Monitor de Notebook (LCD)
- Colorido.
- 16 ou 32 bits por pixel.
- Resolução comum: 1366x768.

### Comparação de Formatos de Imagem

#### Imagem BMP, TIF e TGA
- Colorido ou em escala de cinza.
- Compactação opcional, sem perdas.
- Com ou sem paleta de cores.

#### Imagem GIF
- Colorido, 8 bits por pixel com paleta.
- Compactação sem perdas.

#### Imagem PNG
- Colorido, várias escolhas de bits por pixel.
- Compactação sem perdas.

#### Imagem JPG ou JPEG
- Colorido, compactado com ou sem perdas de qualidade.

## Modelagem Geométrica

### O que é Modelagem Geométrica?
- Área da Computação Gráfica que estuda a criação de **modelos** de objetos reais ou imaginários.
- Descreve e representa a **forma** dos objetos (largura, altura, áreas, etc.).
- Usa uma coleção de **métodos matemáticos** para criar modelos.

### Objetos Gráficos
- Elementos manipulados em Computação Gráfica.
- **Universo físico**: Representação do mundo real.
- **Universo matemático**: Modelagem geométrica em termos de formas e equações.
- **Universo de representação**: Discretização da geometria e atributos.
- **Universo de implementação**: Como os objetos são implementados e manipulados no software.

### Representação de Modelos
- A representação envolve a **discretização** da geometria e de seus atributos.
- A escolha da representação afeta:
  - Estrutura de dados e algoritmos.
  - **Custo de processamento**.
  - Aparência final (quanto se aproxima da realidade).
  - Facilidade de manipulação dos objetos na cena.

### Reconstrução
- Processo inverso da representação, criando **reconstruções aproximadas** de modelos.

### Representação Wireframe (Aramada)
- Representada pela união de segmentos, muito usada nos primeiros estágios da Computação Gráfica.
- **Vantagem**: Exibição rápida.
- **Desvantagem**: Representação ambígua, não define claramente o volume dos objetos.

### Representação por Faces Poligonais
- Utiliza **polígonos**, que são figuras planas fechadas, como triângulos.
- A maioria dos softwares de modelagem e rendering em tempo real utiliza **triângulos**, por demandarem menos memória e tempo de renderização.

### CSG (Geometria Sólida Construtiva)
- Utiliza **primitivas geométricas** combinadas por **transformações espaciais** e **operações booleanas**.
- Muito usada na modelagem de peças mecânicas.

### Modelagem Procedural
- Focada na criação de objetos complexos e fenômenos naturais, como nuvens, chuva e fumaça.
- Gera os objetos com base em **algoritmos e procedimentos**.

### Sistemas de Modelagem
- Conjunto de programas que fornecem métodos para criação e manipulação da geometria ou topologia de objetos gráficos no computador.

## Transformações Geométricas no Plano e no Espaço

### Pontos e Vetores (2D)
- **Ponto**: Denota uma posição no plano.
- **Vetor**: Denota deslocamento, envolvendo direção e magnitude.
- Ambos são expressos por pares de coordenadas em 2D, mas têm significados diferentes: um indica posição, o outro movimento.

### Operações com Pontos e Vetores (2D)
- **Soma de vetores**: Combina vetores para obter um novo deslocamento.
- **Multiplicação por escalar**: Amplia ou reduz o vetor de acordo com um fator.

### Transformações 2D
- **Translação**: Desloca um ponto no plano adicionando um vetor de deslocamento às suas coordenadas.
- **Escala**: Aumenta ou diminui o tamanho de um objeto ao multiplicar as coordenadas por um fator de escala.
- **Rotação**: Gira um ponto em torno da origem de um plano, utilizando um ângulo de rotação.

### Coordenadas Homogêneas
- Permitem representar todas as transformações com uma única matriz de transformação.
- Adiciona-se uma coordenada extra para facilitar operações como translação, escala e rotação de maneira uniforme.
- Os pontos 2D são representados por três coordenadas (x, y, w), onde (x/w, y/w) convertem para coordenadas cartesianas.

### Transformações 2D com Coordenadas Homogêneas
- **Translação**: É representada por uma multiplicação de matriz, o que simplifica o cálculo de várias transformações consecutivas.
- **Escala**: Semelhante à translação, a transformação de escala é representada por uma matriz que modifica o tamanho do objeto em relação ao ponto de origem.
- **Rotação**: A rotação de um ponto em coordenadas homogêneas também é representada por uma matriz, com o ângulo determinando o sentido e magnitude da rotação.

### Transformações 3D com Coordenadas Homogêneas
- As transformações 3D, como em 2D, utilizam coordenadas homogêneas, porém com uma matriz 4x4.
- **Translação**: Movimenta um objeto no espaço tridimensional.
- **Escala**: Altera o tamanho de um objeto nas três dimensões (x, y, z).
- **Rotação**: Pode ocorrer em torno dos eixos x, y ou z, permitindo rotações mais complexas no espaço tridimensional.

### Projeções
- **Projeções** são usadas para representar objetos 3D em um plano 2D.
  - **Projeção Paralela**: Traduz diretamente as coordenadas de um objeto 3D para 2D, eliminando uma das dimensões.
  - **Projeção Perspectiva**: Converge linhas paralelas para um ponto de fuga, simulando a maneira como os objetos distantes parecem menores.

### Projeções Perspectivas
- Um conjunto de retas paralelas converge para um ponto de fuga, simulando profundidade em uma cena 3D.
- Retas paralelas no espaço tendem a se encontrar no infinito, representado por um ponto de fuga na projeção.

### Projeções Paralelas
- Simplificam a projeção ao eliminar uma dimensão, mas podem ser aplicadas em planos diferentes, como projeções oblíquas.

## Iluminação e Tipos de Superfícies

### Comportamento dos Objetos (Superfícies)
- O OpenGL oferece dois modelos para colorização de superfícies, definidos pela função `glShadeModel`:
  - **GL_FLAT**: Cada face da superfície possui uma cor única e simples.
  - **GL_SMOOTH**: Cada face apresenta uma variação de tonalidades, influenciadas pela iluminação na cena.

### Tipos de Iluminação em Ambientes Virtuais
- **Ponto de Luz**: Fonte de luz localizada que ilumina em todas as direções.
- **Luz Direcional Paralela**: A luz vem de uma direção fixa e todos os raios são paralelos.
- **Ponto de Luz Direcional**: Combinação de uma fonte de luz direcional e um ponto de luz específico.
- A luz pode:
  - Vir de uma direção ou posição fixa (ex.: uma lâmpada).
  - Ser o resultado de múltiplas reflexões (luz ambiente), sem uma origem claramente definida.

### Componentes de Luz no OpenGL
- **Luz Ambiente**: Resultante de reflexões no ambiente, vindo de todas as direções.
- **Luz Difusa**: Incide de uma direção específica, é refletida igualmente em todas as direções, mantendo o brilho constante independentemente da posição da câmera.
- **Luz Especular**: Vem de uma direção e é refletida em uma única direção, criando pontos de destaque brilhantes.
- **Luz Emissiva**: Simula a luz que se origina diretamente de um objeto. A cor emissiva adiciona brilho ao objeto, mas não é influenciada por outras fontes de luz na cena.

### Aplicação dos Componentes de Luz nos Materiais
- **Luz Difusa**: Representa superfícies irregulares ou foscas.
- **Luz Especular**: Aparece em superfícies polidas, refletindo a luz em uma direção específica.

### Parâmetros de Luz e Materiais no OpenGL
- Para definir as propriedades de um material:
  - **glMaterialfv(face, pname, params)**:
    - `face`: Especifica a face que será atualizada (GL_FRONT, GL_BACK, GL_FRONT_AND_BACK).
    - `pname`: Parâmetro do material que será alterado (ex.: GL_AMBIENT, GL_DIFFUSE, GL_SPECULAR, etc.).
    - `params`: Novos valores para o parâmetro.

- Para definir as propriedades de um ponto de luz:
  - **glLightfv(light, pname, params)**:
    - `light`: Identificação do ponto de luz (ex.: GL_LIGHT0).
    - `pname`: Parâmetro da luz (ex.: GL_POSITION, GL_DIFFUSE, GL_SPECULAR, etc.).
    - `params`: Novos valores para o parâmetro.

### Habilitação de Iluminação no OpenGL
- Para habilitar o uso de iluminação na cena, usa-se o comando:
  - **glEnable(GL_LIGHTING)**
- Para habilitar um ponto de luz específico:
  - **glEnable(GL_LIGHT0)** (onde "0" é o número do ponto de luz a ser ativado).

