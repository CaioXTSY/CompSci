# Sistemas de Arquivos
### Conceitos Básicos

- **Arquivo**: Unidade lógica de informação criada por um processo.
  - **Definição**: Coleção nomeada de informações armazenadas em um dispositivo físico.
  - **Características**:
    - Informação persistente.
    - Não é afetada pela criação e término de processos.
    - Representa geralmente programas ou dados.

### Nomeação de Arquivos

- **Nome do Arquivo**: Identificador único que permite localizar o arquivo no disco.
- **Extensão do Arquivo**: Indica o tipo de conteúdo (e.g., `.txt`, `.exe`).
- **Regras para Nomeação**:
  - Variam conforme o sistema de arquivos.
  - Exemplos:
    - **Windows**: FAT-16, FAT-32, HPFS, NTFS.
    - **Linux**: EXT2, EXT3, REISERFS, XFS.
    - **Mac OS**: HFS, HFS+.

### Atributos de um Arquivo

Além do nome, um arquivo possui diversos atributos que auxiliam no seu gerenciamento pelo SO:

- **Identificador**: Identifica o arquivo dentro do sistema de arquivos.
- **Localização**: Posição física onde o arquivo está armazenado.
- **Tipo**: Natureza do arquivo (comum, diretório, link simbólico).
- **Tamanho**: Quantidade de dados armazenados.
- **Proteção**: Conjunto de permissões que definem o nível de acesso para usuários e grupos.
- **Timestamp**: Marcas de tempo associadas ao arquivo (data de criação, modificação e acesso).
- **Proprietário**: Usuário ou processo que criou o arquivo.

### Estrutura de Arquivos

Define como os dados estão organizados dentro do arquivo:

- **Sequência de Bytes**: Forma mais simples de organização.
- **Arquivo de Registro**: Organiza dados em registros ou campos; frequentemente usado em bancos de dados.
  - **Estruturas**:
    - Sequência linear de registros.
    - Arquivos indexados no formato chave/valor.
- **Arquivo de Texto**: Texto puro formado por linhas separadas por caracteres de controle (`\n` no Linux e `\r\n` no Windows).
- **Arquivos de Código**: Divididos internamente em várias seções para conter código, tabela de símbolos, lista de dependências, etc.
  - **Exemplos**:
    - **ELF (Executable and Linking Format)**: Utilizado em sistemas baseados em UNIX.
    - **PE (Portable Executable)**: Utilizado em plataformas Windows.

### Identificação de Conteúdo

Os SOs e aplicações muitas vezes precisam identificar o conteúdo dos arquivos para processá-los corretamente. Diversas soluções são adotadas:

- **Extensão do Nome do Arquivo** (DOS/Windows): A extensão (e.g., `.txt`, `.exe`) indica o tipo de arquivo.
- **Números Mágicos** (UNIX): Identificam o tipo de arquivo através dos bytes iniciais do arquivo.
- **Atributos Adicionais** (MacOS 9): Utilizam campos específicos para definir o tipo e o criador do arquivo.
- **Padrão MIME (Multipurpose Internet Mail Extensions)**: Define tipos de arquivos na forma `tipo/subtipo` (e.g., `text/plain`, `image/jpeg`).

### Tipos de Arquivos

Além dos arquivos comuns, existem outros tipos de arquivos utilizados para propósitos específicos:

- **Diretórios**: Arquivos que mantêm a estrutura do sistema de arquivos.
- **Arquivos de Dispositivo**: Abstrações para dispositivos de entrada/saída (e.g., `/dev/ttyS0`, `/dev/sda1` no Linux).
- **Arquivos Virtuais**: Representam informações internas do núcleo do SO, processos e drivers de dispositivos (e.g., `/proc/cpuinfo`).
- **Arquivos de Comunicação**: Utilizados como interface para canais de comunicação do protocolo TCP/IP.
- **Arquivos Especiais de Blocos**: Usados para modelar discos.

---

## 3. Diretórios

### Fatos Básicos

- **Diretórios (Pastas)**: Utilizados para organizar e controlar o acesso aos arquivos no sistema de arquivos.
- **Representação**: Em muitos SOs, diretórios também são representados por arquivos especiais.

### Estruturas de Diretórios

Podem ser classificadas em duas estruturas básicas:

1. **Nível Único**:
   - **Descrição**: Um único diretório-raiz que contém todos os arquivos.
   - **Exemplo**: Sistemas de arquivos antigos ou muito simples.
   - **Vantagem**: Simplicidade.
   - **Desvantagem**: Escalabilidade limitada; difícil de gerenciar grandes quantidades de arquivos.

2. **Hierárquicos**:
   - **Descrição**: Organização em árvore, agrupando arquivos relacionados em subdiretórios.
   - **Exemplo**: Sistemas modernos como Windows, Linux, MacOS.
   - **Vantagem**: Melhor organização e escalabilidade.
   - **Desvantagem**: Complexidade adicional na navegação e gerenciamento.

### Nome de Caminhos

Aplicado a diretórios hierárquicos, comumente adotando dois métodos:

- **Caminho Absoluto**:
  - **Descrição**: Especifica a localização completa do arquivo na árvore de diretórios.
  - **Exemplo**: `/usr/ast/postal`.
  - **Vantagem**: Único e não dependente do diretório atual.
  - **Desvantagem**: Mais longo e menos flexível.

- **Caminho Relativo**:
  - **Descrição**: Especifica a localização em relação ao diretório atual.
  - **Exemplo**: `ast/postal`.
  - **Vantagem**: Mais curto e flexível.
  - **Desvantagem**: Depende do diretório atual, podendo levar a ambiguidades.

### Implementação de Diretórios

#### Mapeamento de Nomes

- **Função Principal**: Mapear o nome do arquivo em ASCII para as informações necessárias para localizar os dados no disco.
- **Entradas do Diretório**:
  - Nome do arquivo.
  - Tipo e tamanho.
  - Proprietário e proteção.
  - Data de criação e modificação.
  - Lista de blocos usados.

#### Estruturas de Diretórios

1. **Diretório Simples (MS-DOS/Windows)**:
   - **Características**:
     - Entradas de dimensão fixa.
     - Cada entrada contém endereços de disco e atributos.
   - **Vantagem**: Simplicidade na implementação.
   - **Desvantagem**: Limitação no número de arquivos e flexibilidade.

2. **Referenciando I-nodes (UNIX/Linux)**:
   - **Características**:
     - Cada entrada no diretório refere-se a um i-node.
     - Suporte a nomes de arquivos longos e tamanhos variáveis.
   - **Vantagem**: Maior flexibilidade e escalabilidade.
   - **Desvantagem**: Implementação mais complexa.

#### Suporte a Nomes Longos

- **Desafio**: Permitir que os sistemas operacionais modernos suportem nomes de arquivos longos e com tamanhos variáveis.
- **Soluções**:
  - Utilização de estruturas dinâmicas para armazenar nomes de arquivos.
  - Armazenamento eficiente de metadados para evitar desperdício de espaço.

---

## 4. Implementação do Sistema de Arquivos

### Esquema do Sistema de Arquivos

1. **Armazenamento em Disco**:
   - Discos são divididos em partições.
   - **MBR (Master Boot Record)**:
     - Localizado no setor 0 do disco.
     - Contém a tabela de partições.
     - **Função**: Quando o computador é iniciado, a BIOS lê e executa o MBR para carregar o sistema operacional.

2. **Estrutura Básica de um Sistema de Arquivos**:
   - **Bloco de Inicialização**: Primeiro bloco de uma partição a ser lido.
   - **Superbloco**: Contém informações críticas como número de blocos, tipo do sistema de arquivos, etc.
   - **Gerenciamento do Espaço Livre**:
     - Mapa de bits ou lista de ponteiros.
   - **I-nodes**: Estruturas de dados que armazenam informações dos arquivos (localização, atributos, etc.).

3. **Diretório Raiz**:
   - Topo da árvore de diretórios.
   - Contém todos os arquivos e subdiretórios do sistema.

### Técnicas de Alocação de Arquivos

1. **Alocação Contígua**:
   - **Descrição**: Armazena um arquivo em blocos sequenciais no disco.
   - **Vantagem**: Bom desempenho em acessos sequenciais e diretos.
   - **Desvantagem**:
     - Dificuldade em alocar espaços contíguos para arquivos que podem crescer.
     - Fragmentação externa, limitando a flexibilidade.

   - **Soluções para Mitigar Desvantagens**:
     - Técnicas de alocação **first-fit**, **best-fit**, **worst-fit**.
     - **Desfragmentação de Disco**: Operação lenta que reorganiza os blocos para criar espaços contíguos livres.

   - **Uso Ideal**: Sistemas dedicados a reprodução de dados multimídia, onde arquivos não são modificados frequentemente.

2. **Alocação com Lista Encadeada**:
   - **Descrição**: Arquivos são compostos por blocos ligados por ponteiros.
   - **Vantagem**:
     - Flexibilidade na alocação; arquivos podem ser expandidos ou reduzidos facilmente.
     - Elimina fragmentação externa.
   - **Desvantagem**:
     - Acesso sequencial lento; difícil acessar blocos intermediários.
     - Desperdício de espaço devido ao armazenamento de ponteiros em cada bloco.
     - Relativa fragilidade em relação a erros nos blocos do disco.

   - **Melhoria com FAT (File Allocation Table)**:
     - Utiliza uma tabela centralizada para gerenciar os blocos.
     - **Vantagem**: Blocos livres indicados por flags específicos.
     - **Desvantagem**: Consumo elevado de memória para tabelas em discos grandes.

3. **Alocação com Lista Encadeada e Índice**:
   - **I-nodes**:
     - Cada arquivo possui um i-node que contém índices dos blocos no disco.
     - **Vantagem**: Acesso direto eficiente; menor uso de memória comparado ao FAT.
     - **Desvantagem**: Implementação mais complexa.

### Gerência de Espaço em Disco

1. **Mapa de Bits**:
   - **Descrição**: Pequeno conjunto de blocos no início da partição para manter um mapa de bits.
   - **Funcionamento**: Cada bit representa um bloco lógico do disco (livre ou ocupado).
   - **Exemplo**:
     - Disco de 80 GBytes com blocos de 4.096 bytes.
     - Necessário: 20.971.520 bits (~2.621.440 bytes ou 640 blocos).

2. **Lista de Blocos Livres**:
   - **Descrição**: Cada bloco livre contém um ponteiro para o próximo bloco livre.
   - **Desvantagem**: Exige um acesso a disco para cada bloco livre requisitado.
   - **Melhoria com FAT**: Blocos livres são indicados por flags específicos na tabela de alocação, reduzindo a necessidade de múltiplos acessos.

### Implementação de Diretórios

- **Mapeamento de Nomes**: Diretórios mapeiam nomes de arquivos para informações necessárias para localizar os dados.
- **Estrutura de Diretórios**:
  - **Diretórios Simples**: Entradas de dimensão fixa com endereços de disco e atributos.
  - **Diretórios Referenciando I-nodes**: Cada entrada refere-se a um i-node, permitindo maior flexibilidade e suporte a nomes longos.

### Sistemas de Arquivos Virtuais

- **Gerenciamento de Acesso**:
  - Verificação de permissões de acesso.
  - Controle de concorrência (atribuição e liberação de travas).
  - Manutenção de informações sobre arquivos abertos pelos processos.
- **Independência do Dispositivo Físico**:
  - Estruturas de controle são independentes do dispositivo de armazenamento e da estratégia de alocação utilizada.
- **Exemplos em UNIX**:
  - `/proc/cpuinfo`: Informações sobre os processadores disponíveis.
  - `/proc/[PID]/maps`: Disposição das áreas de memória alocadas para um processo específico.
  - `/sys/block/sda/queue/scheduler`: Política de escalonamento de disco para acesso ao disco `/dev/sda`.

### Exemplos de Estrutura de Arquivos

#### Arquivo de Registro

- **Registros em Sequência**: Dados organizados em sequência linear.
- **Registros Indexados**: Utilizam chaves para acesso rápido (e.g., bancos de dados).

#### Arquivo de Texto

- **Exemplo**: `Hello.c`
- **Representação**: Sequência de bytes (representação em hexadecimal).

#### Arquivo de Código (ELF)

- **Composição**:
  - **ELF Header**: Informações gerais sobre o arquivo.
  - **Section Header Table**: Descrição de cada seção.
  - **Sections**: Trechos que compõem o arquivo (código binário, constantes, tabelas de símbolos, etc.).
  - **Program Header Table**: Informações sobre como o código deve ser carregado na memória.
  - **Segments**: Conteúdo que deve ser carregado de cada segmento.

### Exemplos de Implementação

#### Alocação Contígua

- **Problema**: Como alocar um arquivo com 10 blocos?
  - **Solução**: Encontrar 10 blocos sequenciais livres.
- **Vantagens e Desvantagens**:
  - **Vantagem**: Robustez a falhas de disco.
  - **Desvantagem**: Dificuldade em determinar o espaço necessário para arquivos que podem crescer (fragmentação externa).

#### Lista Encadeada com Tabela na Memória

- **Problema**: Grandes tabelas de alocação ocupam muita memória.
  - **Exemplo**: Disco de 200GB com blocos de 1KB requer 200 milhões de entradas, ocupando 600MB de memória.
- **Solução**: Utilizar i-nodes para armazenar índices de blocos no disco, reduzindo o uso de memória.

### Gerência de Espaço em Disco

- **Exemplo de Cálculo de Tempo para Ler um Bloco**:
  - **Dados**:
    - Blocos: 131.072 bytes por trilha.
    - Tempo de rotação: 8,33 ms.
    - Tempo médio de busca: 10 ms.
    - Atraso rotacional: 4,165 ms.
  - **Cálculo**:
    - Tempo total = Tempo de busca + Atraso rotacional + (k / 131.072) * 8,33 ms
    - Onde `k` é o tamanho do bloco em bytes.

### Implementação de Arquivos Compartilhados

- **Modelo de Grafo Acíclico Orientado**:
  - Usuários B e C compartilham um mesmo arquivo.
  - **Vantagem**: Permite compartilhamento eficiente.
  - **Desvantagem**: Necessidade de mecanismos de sincronização para evitar conflitos.

