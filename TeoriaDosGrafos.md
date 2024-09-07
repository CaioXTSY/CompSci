# Teoria Dos Grafos 
A teoria dos grafos é uma área da matemática e ciência da computação que estuda as relações entre objetos. Seu primeiro uso registrado data de 1736, associado a Leonhard Euler.

# História dos Grafos

## Leonhard Euler (1736)
- Problema das Pontes de Königsberg: Primeira formulação do conceito de grafos.

## Gustav Kirchoff (1824–1887)
- Aplicou grafos em circuitos elétricos, introduzindo as "árvores matemáticas".

## Arthur Cayley (1821–1895)
- Expandiu o uso de grafos para a química, enumerando isômeros de hidrocarbonetos.

# O que são Grafos?

Um **grafo** é uma estrutura de dados fundamental na ciência da computação e matemática, usada para modelar relações entre um conjunto de objetos.

## Vértices

- **Vértices** (também chamados de **nós**): são os objetos individuais do grafo.
- Exemplos: Em um grafo de rede social, cada pessoa pode ser um vértice.

## Arestas

- **Arestas**: são as conexões entre os vértices.
- Podem ser **direcionadas** (indicando uma relação unidirecional) ou **não direcionadas** (indicando uma relação bidirecional).
- Exemplos: Em um grafo de rede social, uma aresta pode representar uma amizade ou uma conexão entre duas pessoas.

# Definição Formal de um Grafo

Um grafo `G` é uma tripla ordenada `(V(G), E(G), ψG)` que consiste em:

1. **Conjunto de Vértices (`V(G)`)**: Um conjunto não vazio de vértices.
2. **Conjunto de Arestas (`E(G)`)**: Um conjunto de arestas.
3. **Função de Incidência (`ψG`)**: Associa cada aresta de `G` a um par não ordenado de vértices (não necessariamente distintos) de `G`.

Se `e` é uma aresta e `u` e `v` são vértices tais que `ψG(e) = uv`, diz-se que `e` liga `u` e `v`. Os vértices `u` e `v` são chamados de extremidades de `e`.

## Exemplo 1

- **Grafo `G`**: `(V(G), E(G), ψG)`
- **Vértices `V(G)`**: `{v1, v2, v3, v4, v5}`
- **Arestas `E(G)`**: `{e1, e2, e3, e4, e5, e6, e7, e8}`
- **Função de Incidência `ψG(e)`**:
  - `ψG(e1) = v1v2`
  - `ψG(e2) = v2v3`
  - `ψG(e3) = v3v3`
  - `ψG(e4) = v3v4`
  - `ψG(e5) = v2v4`
  - `ψG(e6) = v4v5`
  - `ψG(e7) = v2v5`
  - `ψG(e8) = v2v5`

## Exemplo 2

- **Grafo `H`**: `(V(H), E(H), ψH)`
- **Vértices `V(H)`**: `{u, v, w, x, y}`
- **Arestas `E(H)`**: `{a, b, c, d, e, f, g, h}`
- **Função de Incidência `ψH`**:
  - `ψH(a) = uv`
  - `ψH(b) = uu`
  - `ψH(c) = uw`
  - `ψH(d) = wx`
  - `ψH(e) = vx`
  - `ψH(f) = wx`
  - `ψH(g) = ux`
  - `ψH(h) = xy`

# Isomorfismo de Grafos

O isomorfismo de grafos é um conceito chave na teoria dos grafos, usado para determinar se dois grafos são essencialmente os mesmos, apesar de suas possíveis representações visuais diferentes.

## Definição e Características

- **Isomorfismo de Grafos**: Dois grafos `G` e `H` são isomórficos (indicado por `G ≅ H`) se existir uma correspondência biunívoca entre seus vértices que preserve as adjacências.

## Complexidade do Problema

- **Desafio Computacional**: Determinar o isomorfismo de grafos é um problema complexo, especialmente para grafos grandes.
- **Classe NP**: Está na classe NP, mas não se sabe se é NP-completo ou pertence a P.

# Principais Classes e Terminologias de Grafos

## Terminologia Básica

- **Nós Terminais**: Conjunto de um ou dois vértices que formam uma aresta.
- **Laço (Loop)**: Aresta que tem apenas um nó terminal.
- **Arestas Paralelas**: Arestas associadas ao mesmo conjunto de vértices.
- **Vértices Adjacentes**: Vértices conectados por uma aresta.
- **Arestas Adjacentes**: Duas arestas incidentes em um vértice comum.

## Propriedades dos Vértices

- **Vértice Adjacente a Si Próprio**: Vértice que é nó terminal de um laço.
- **Vértice Isolado**: Vértice sem nenhuma aresta incidente.
- **Grau do Vértice**: Número de arestas incidentes a um vértice (laços contam duas vezes).

## Tipos de Grafos

### Grafo Vazio
- **Definição**: Um grafo sem vértices nem arestas.

### Grafo Simples
- **Características**: Sem laços nem arestas paralelas.
- **Aplicações**: Muitas aplicações podem ser modeladas como grafos simples.

### Grafo Não Direcionado
- **Propriedade**: Se um vértice `u` está ligado a `v`, então `v` está ligado a `u`.

### Grafos Direcionados (Dígrafos)
- **Arestas Dirigidas**: Arestas associadas a um par ordenado de vértices.

### Grafo Completo
- **Notação**: `Kn` para um grafo completo com `n` vértices.
- **Propriedade**: Todo vértice é adjacente a todos os outros.

### Grafo Bipartido
- **Divisão**: Vértices divididos em dois subconjuntos, com arestas apenas entre vértices de subconjuntos diferentes.

### Grafo Valorado
- **Característica**: Cada aresta tem um valor (ou peso) associado.

## Outros Tipos de Grafos

- **Grafo Simples**
- **Multigrafo**
- **Pseudografo**
- **Grafo Dirigido**
- **Multigrafo Dirigido**

## Subgrafo
- **Definição**: Um subconjunto de vértices e arestas de um grafo maior.


## Graus dos Vértices

- **Propriedade Fundamental**: A soma dos graus de todos os vértices de um grafo é sempre um número par, pois cada aresta contribui com 2 ao grau total.
- **Corolário**: Em qualquer grafo, existe um número par de vértices com grau ímpar.

### Exemplos de Aplicação
1. **Grafo com Vértices de Graus 1, 1, 2, e 3**: 
   - **É possível?** Não, pois o grau total seria 7, um número ímpar.
2. **Grafo com Vértices de Graus 1, 1, 3, e 3**: 
   - **É possível?** Sim, pois o grau total é 8, um número par.
3. **Grafo com 10 Vértices de Graus 1, 1, 2, 2, 2, 3, 4, 4, 4, e 6**: 
   - **É possível?** Não, por duas razões:
     - **Três vértices de grau ímpar** violam o corolário acima.
     - **Grau total de 29** é ímpar, o que é impossível para qualquer grafo.

## Grafo Regular

- **Definição**: Um grafo é regular se todos os seus vértices têm o mesmo grau.
- **Exemplo**: Todos os grafos completos são regulares.

### Grafo Direcionado Regular
- **Condição Adicional**: O grau de saída e entrada de cada vértice deve ser igual.

# Representação Computacional de Grafos e Complexidade de Algoritmos

## Análise de Complexidade de Algoritmos
- **Importância**: Projetar algoritmos eficientes desde o início pode economizar recursos e tempo de execução significativos.
- **Comparação de Algoritmos**: Analisar a complexidade de algoritmos diferentes permite escolher a opção mais eficiente.

## Complexidade de Tempo e Espaço
- **Tempo de Execução**: Medido pelo número de operações como função do tamanho da entrada `n`.
- **Espaço de Memória**: Quantidade de memória usada, um fator importante para algoritmos que trabalham com grandes conjuntos de dados.

## Notações de Complexidade de Tempo
- Indica o comportamento do algoritmo em diferentes casos: pior (`O`), melhor (`Ω`), e médio (`Θ`).
- Classes de complexidade comuns incluem: `O(1)`, `O(n)`, `O(n log n)`, `O(n^2)`, `O(2^n)`, `O(n!)`.

## Representações de Grafos
- **Matriz de Incidência**: Uma matriz `n x m` que relaciona vértices a arestas. Cada coluna tem dois `1`s indicando os vértices que a aresta conecta.
- **Matriz de Adjacência**: Uma matriz `n x n` onde cada elemento indica se existe uma aresta entre um par de vértices.

### Matriz de Adjacência para Grafos Não Direcionados
- A matriz é simétrica em relação à diagonal principal.

### Matriz de Adjacência para Grafos Direcionados
- A matriz reflete a direção das arestas entre os vértices.

## Observações sobre Matriz de Adjacência
- **Grafos Simples**: O grau de um vértice é a soma dos elementos em sua linha ou coluna.
- **Sem Laços**: Diagonal principal com zeros.
- **Simetria**: Em grafos não direcionados, a matriz é simétrica em relação à diagonal.

A matriz de adjacência é uma forma prática de representar grafos em computadores, mas para grafos com muitos vértices e poucas arestas (grafos esparsos), outras estruturas de dados como listas de adjacências podem ser mais eficientes em termos de espaço.

# Lista de Adjacências e Detecção de Vértice Sink

## Lista de Adjacências
- Representa um grafo como um vetor de listas.
- Cada lista corresponde a um vértice e contém todos os vértices adjacentes.
- Eficiente para grafos esparsos com `O(V + E)` de complexidade de espaço.

## Escolhendo a Representação Apropriada
- **Matriz de Incidência**: Adequada quando precisamos manter uma relação entre vértices e arestas.
- **Matriz de Adjacência**: Ideal para grafos densos, permite verificar a existência de uma aresta em `O(1)`.
- **Lista de Adjacência**: Geralmente preferida, especialmente para grafos esparsos.

## Isomorfismo e Matrizes de Adjacência
- Verificar isomorfismo "força-bruta" pode exigir a comparação de várias propriedades estruturais e a permutação de matrizes.

## Determinando um Vértice Sink em um Grafo Dirigido
KKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKKK

# Tipos de Caminhamentos em Grafos

Os grafos podem ser explorados através de diferentes tipos de caminhamentos, que são sequências de vértices e arestas. Aqui estão as definições e características de cada tipo:

## Caminho (Walk)
- **Definição**: Uma sequência alternada de vértices e arestas adjacentes.
- **Características**:
  - Pode ter vértices e arestas repetidos.
  - Possui um vértice inicial e final.
  - O tamanho é o número de arestas no caminho.

## Caminho Fechado (Closed Walk)
- **Definição**: Um caminho que começa e termina no mesmo vértice.
- **Características**:
  - Vértices e arestas podem se repetir.
  - Se tem pelo menos uma aresta, é chamado de ciclo.

## Trajeto (Path)
- **Definição**: Um caminho sem arestas repetidas.
- **Características**:
  - Nenhuma aresta é percorrida mais de uma vez.
  - Pode ter vértices repetidos (exceto em trajetos simples).

## Trajeto Simples (Simple Path)
- **Definição**: Um caminho sem arestas nem vértices repetidos.
- **Características**:
  - Todos os vértices e arestas são distintos.

## Circuito (Circuit)
- **Definição**: Um trajeto fechado sem arestas repetidas.
- **Características**:
  - O vértice inicial e final são idênticos.
  - Pode ter vértices repetidos (exceto em circuitos simples).

## Circuito Simples (Simple Circuit)
- **Definição**: Um trajeto fechado onde não há arestas e vértices repetidos, exceto os vértices inicial e final que são idênticos.
- **Características**:
  - Também conhecido como ciclo simples.


## Terminologia de Caminhamentos

| Tipo                            | Aresta Repetida? | Vértice Repetido? | Começa e Termina no Mesmo Vértice? |
|---------------------------------|------------------|-------------------|------------------------------------|
| Caminho (Walk)                  | Pode             | Pode              | Pode                               |
| Caminho Fechado (Closed Walk)   | Pode             | Pode              | Sim                                |
| Trajeto (Path)                  | Não              | Pode              | Pode                               |
| Trajeto Simples (Simple Path)   | Não              | Não               | Não                                |
| Circuito (Circuit)              | Não              | Pode              | Sim                                |
| Circuito Simples (Simple Circuit)| Não              | Não (exceto extremidades) | Sim                            |

# Conectividade em Grafos

## Conectividade
- **Definição**: Um grafo é **conexo** se, para qualquer par de vértices `u` e `v`, existe um caminho de `u` para `v`.
- **Formalização**: `G é conexo ⟺ ∀ vértices u, v ∈ V(G), ∃ um caminho de u para v`.

### Fundamentos da Conectividade
- **Lema a**: Em um grafo conexo, qualquer par de vértices distintos pode ser conectado por um trajeto simples.
- **Lema b**: Se `u` e `v` estão em um circuito e uma aresta é removida, ainda existe um trajeto de `u` para `v`.
- **Lema c**: Se `G` é conexo e contém um circuito, uma aresta do circuito pode ser removida sem desconectar `G`.
- **Teorema**: Um grafo é bipartido se e somente se não contém nenhum ciclo de tamanho ímpar.

## Circuito Euleriano

### Definições
- **Circuito Euleriano**: Um circuito que começa e termina no mesmo vértice, passando exatamente uma vez por cada aresta de `G`.
- **Trajeto Euleriano**: Uma sequência que começa em um vértice `u`, termina em um vértice `v`, e passa por cada aresta de `G` exatamente uma vez.

### Teoremas
- **Teorema 1**: Se `G` possui um circuito euleriano, então todos os vértices de `G` têm grau par.
- **Teorema 2**: Se algum vértice de `G` tem grau ímpar, `G` não possui um circuito euleriano.
- **Teorema 3**: Se `G` é conexo, não vazio, e todos os vértices têm grau par, então `G` possui um circuito euleriano.

### Corolário do Trajeto Euleriano
- Existe um trajeto euleriano de `u` para `v` em `G` se `G` é conexo e exatamente dois vértices, `u` e `v`, têm grau ímpar, com todos os outros vértices tendo grau par.

### Problema das Pontes de Königsberg
- É um exemplo clássico que questiona a existência de um percurso que passe por todas as pontes da cidade exatamente uma vez. Este problema levou à formulação dos conceitos de grafos e circuitos eulerianos.

# Algoritmo de Fleury e Determinação de Grafos Eulerianos

## Algoritmo de Fleury para Circuitos Eulerianos

**Objetivo**: Encontrar um circuito Euleriano em um grafo Euleriano.

**Passos do Algoritmo**:
1. **Iniciar**: Comece em qualquer vértice `v`.
2. **Escolha da Aresta**:
   - Escolha a próxima aresta para atravessar de modo a não desconectar o grafo.
   - Se todas as arestas restantes desconectariam o grafo, escolha qualquer uma delas (`bridge`).
3. **Exclusão e Continuação**:
   - Atravesse para o vértice no final da aresta escolhida.
   - Exclua a aresta do grafo.
   - Se houver vértices isolados resultantes da exclusão da aresta, remova-os também.
4. **Repetir**: Repita o processo até que todas as arestas tenham sido usadas.

**Garantia**: Esse algoritmo sempre produz um circuito Euleriano se o grafo for Euleriano.

## Determinação de Grafos Eulerianos

Um grafo é Euleriano se ele é conexo e cada vértice tem um grau par.

**Exemplos para Análise**:
- **Grafo Completo K2**: Não é Euleriano, pois possui apenas dois vértices com grau 1.
- **Grafo Bipartido Completo K3,3**:
  - É Euleriano, já que é conexo e todos os vértices têm grau 3 (ímpar, portanto não é Euleriano).
- **Grafo Cubo**:
  - É Euleriano, pois é um grafo regular com todos os vértices de grau 3 (ímpar, portanto não é Euleriano).
- **Grafo Octaedro**:
  - É Euleriano, pois é um grafo regular com todos os vértices de grau 4 (par e conexo).
- **Grafo de Petersen**:
  - Não é Euleriano, pois é um grafo regular com grau 3 para cada vértice (ímpar).

-- slide 5 aqui
# Circuitos Eulerianos e Hamiltonianos em Grafos

## Circuitos em Grafos
- **Circuito Euleriano**: Um circuito que inclui todas as arestas de um grafo conectado exatamente uma vez.
- **Circuito Hamiltoniano**: Um circuito que passa exatamente uma vez por cada vértice de um grafo.

## Distinção entre os Circuitos
- **Euleriano**:
  - Inclui todas as arestas exatamente uma vez.
  - Vértices podem ser repetidos (exceto os vértices inicial e final que são idênticos).
- **Hamiltoniano**:
  - Inclui todos os vértices exatamente uma vez (exceto os vértices inicial e final que são idênticos).
  - Pode não incluir todas as arestas.
  - Pode não gerar um circuito Euleriano.

## Condições para Existência
- **Circuito Euleriano**:
  - Um grafo possui um circuito Euleriano se e somente se é conexo e todos os vértices têm grau par.
- **Circuito Hamiltoniano**:
  - Não há uma condição necessária e suficiente conhecida para determinar se um grafo possui um circuito Hamiltoniano.
  - Teoremas como o de Ore e Dirac fornecem condições suficientes sob certas circunstâncias.

### Teoremas Relevantes
- **Teorema de Ore (1960)**: Se `G` é um grafo simples com `n (≥ 3)` vértices, e `deg(u) + deg(v) ≥ n` para cada par não adjacentes de vértices `u` e `v`, então `G` é Hamiltoniano.
- **Teorema de Dirac (1952)**: Se `G` é um grafo simples com `n (≥ 3)` vértices, e `deg(v) ≥ n/2` para cada vértice `v`, então `G` é Hamiltoniano.

## Problemas Clássicos Relacionados
- **Problema do Carteiro Chinês**:
  - Também conhecido como problema de roteamento de entrega, pode ser resolvido eficientemente quando o grafo é Euleriano.
- **Problema do Caixeiro Viajante**:
  - Relacionado ao ciclo Hamiltoniano, é NP-Completo e não se conhece um algoritmo eficiente para resolvê-lo.
  - Existem algoritmos heurísticos e de força bruta para encontrar soluções aproximadas.

## Aplicações Práticas
- **Coleta de lixo, entregas e limpeza de ruas**: Problema do Carteiro Chinês.
- **Planejamento de rotas e logística**: Problema do Caixeiro Viajante.

## Casos Especiais do Problema do Caixeiro Viajante
- **PCV Métrico**: Onde as distâncias satisfazem a desigualdade triangular.
- **PCV Euclideano**: Onde as distâncias são euclidianas.
- **PCV Assimétrico**: Onde a distância de viagem entre dois vértices depende da direção da viagem.

# O Problema do Caminho Mínimo

O problema do caminho mínimo consiste em encontrar, em um grafo ponderado, o subgrafo que representa o caminho de peso mínimo entre vértices específicos. Existem variantes do problema que incluem:

- **Caminho mínimo de fonte única**: Encontrar o caminho mais curto de um vértice específico para todos os outros vértices no grafo.
- **Caminho mínimo entre todos os pares**: Encontrar o caminho mais curto entre cada par de vértices no grafo.

## Algoritmos para o Problema do Caminho Mínimo

### Caminhos Mínimos de Fonte Única

#### Algoritmo de Bellman-Ford
- Utilizado quando os grafos contêm arestas com pesos negativos.
- Capaz de detectar ciclos de peso negativo.

#### Algoritmo de Dijkstra
- Resolve o problema em grafos onde os pesos das arestas são não negativos.
- Funcionamento:
  - Calcula a menor distância do vértice inicial aos seus vizinhos.
  - Repete o processo para os vizinhos e seus respectivos vizinhos, atualizando as menores distâncias encontradas.

### Limitações do Algoritmo de Dijkstra
- Não funciona corretamente se houver arestas com pesos negativos.
- Calcula os caminhos mínimos somente a partir de uma única origem.
- Para encontrar caminhos mínimos de todos os vértices para todos os outros, é necessário executar o algoritmo para cada vértice, resultando em uma complexidade total de `O(V * E)` na implementação mais simples, onde `V` é o número de vértices e `E` é o número de arestas.

### Caminho Mínimo de Fonte Única em Grafos Acíclicos Dirigidos
- Algoritmos específicos podem ser utilizados para grafos acíclicos, que são mais eficientes, uma vez que esses grafos não têm ciclos e, portanto, não podem ter ciclos de peso negativo.

## Aplicações Práticas
- Sistemas de navegação GPS.
- Redes de telecomunicação.
- Planejamento e roteirização logística.

# Árvores

## Definições

- **Árvore**: Um grafo conexo e sem ciclos (grafos simples) em que há somente um caminho entre qualquer par de vértices.
- **Subárvore**: Um subgrafo conexo e acíclico de uma árvore.
- **Floresta**: Um grafo que não contém ciclos, podendo ou não ser conexo.

## Fundamentos

- **Teorema**: Seja `G` um grafo com `n` vértices. Então, o seguinte é equivalente:
  1. `G` é uma árvore;
  2. `G` não contém ciclos e possui `n - 1` arestas;
  3. `G` está conectado e tem `n - 1` arestas;
  4. `G` está conectado e cada aresta é uma ponte;
  5. Quaisquer dois vértices de `G` são conectados por exatamente um caminho;
  6. `G` não contém ciclos, mas a adição de qualquer nova aresta cria exatamente um ciclo.

- **COROLÁRIO**: Se `G` for uma floresta com `n` vértices e `k` componentes, então `G` terá `n - k` arestas.

## Árvore Geradora

- Transformar um grafo `G` conectado em árvore:
  1. Escolher um ciclo e remover qualquer uma de suas arestas. O grafo resultante permanece conectado.
  2. Repetir este procedimento com os ciclos restantes, continuando até que não haja mais ciclos.
- O grafo resultante é uma árvore que conecta todos os vértices de `G`, denominada **árvore geradora** de `G`.
- **Floresta Geradora**: Realizar este procedimento em cada componente de `G` se `G` é um grafo com `n` vértices, `m` arestas e `k` componentes.

## Árvore Geradora Mínima (Minimal Spanning Tree)

- **Definição**: Uma árvore geradora mínima para um grafo com peso é uma árvore geradora que tem o menor peso total possível dentre todas as possíveis árvores geradoras do grafo.

## Algoritmos para obter a AGM

### Complexidade dos Algoritmos

- A complexidade dos algoritmos evoluiu de `O(n^2)` para `O(n)`, com uma implementação datada de 2008.

### Os Mais Básicos

- **Algoritmo de Kruskal** e **Algoritmo de Prim** são dois dos algoritmos mais populares e gulosos para determinação de árvores geradoras mínimas.

### Algoritmo de Kruskal

- Abordagem gulosa: adiciona à floresta uma aresta de menor peso possível a cada etapa.
- Usa uma estrutura de dados de conjuntos disjuntos para manter vários conjuntos disjuntos de elementos, cada um contendo os vértices em uma árvore da floresta atual.

# Algoritmo de Prim

- Proposto originalmente em 1930 por Vojtěch Jarník, em 1957 por Robert C. Prim, e redescoberto por Edsger Dijkstra em 1959.
- Inclui, de forma gulosa, vértices na árvore geradora mínima um a um.
- Propriedade: as arestas no conjunto A sempre formam uma árvore única, começando em um vértice raiz arbitrário `r` e aumentando até que a árvore abranja todos os vértices em `V`.
- Cada etapa adiciona à árvore `A` uma aresta leve que conecta `A` a um vértice isolado.
- Implementação eficiente necessita de uma fila de prioridades classificada pelos pesos das arestas.

# Voltando ao Problema do Caixeiro Viajante

- Consiste em determinar um ciclo hamiltoniano de custo mínimo em um grafo ponderado, direcionado ou não.
- **PCV vs. AGM**: Aplicar o algoritmo de AGM em um grafo completo fornece um limite inferior para a solução do PCV.

## Como encontrar o limite inferior para o PCV?

- Qualquer ciclo hamiltoniano em um grafo completo ponderado, ao remover um vértice, torna-se um caminho semi-hamiltoniano e deve ser uma árvore geradora.

# Algoritmo de Christofides para o PCV

- Heurística para encontrar soluções aproximadas para o PCV, garantindo soluções no máximo 1,5 vezes piores do que a ótima.
- Publicado por Nicos Christofides em 1976.

## Etapas do Algoritmo de Christofides

1. Criar uma árvore geradora mínima `T` de `G`.
2. Seja `O` o conjunto de vértices de grau ímpar em `T`.
3. Encontrar um casamento perfeito de peso mínimo `M` no subgrafo induzido pelos vértices de `O`.
4. Combinar as arestas de `T` e `M` para formar um multigrafo `H` em que cada vértice tem grau par.
5. Formar um circuito Euleriano em `H`.
6. Transformar o circuito Euleriano em um circuito Hamiltoniano, ignorando vértices repetidos.

# Outras Aplicações

## Rede Ferroviária

- Conectar cidades minimizando a quantidade total de trilhos.

## Enumeração de Moléculas Químicas

- Estruturas moleculares como árvores.

## Árvores de Busca

- Estruturas de dados para busca eficiente.

## Otimização de Sistemas Submersos Off-Shore

- Minimizar tubulações conectando poços a plataformas.

## Redes Ópticas

- Otimizar a distribuição de sinal através de splitters.

## Distribuição de Sinal em Redes

- Minimizar custos de distribuição e decodificação.

## Projeto de Redes

- Computadores, comunicações, telefônicas, hidráulicas, elétricas, de petróleo e gás.
- Análise de agrupamentos, genética, astronomia (quasars), limites de problemas NP-Difíceis, computação móvel.
