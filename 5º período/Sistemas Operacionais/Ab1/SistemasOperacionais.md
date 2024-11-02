# Sistemas Operacionais

### O que são Sistemas Operacionais?

#### Definição
- **Sistema Operacional (SO)**: Conjunto de ferramentas que fornecem serviços, criando uma interface entre aplicações e hardware, gerenciando os recursos de hardware e compartilhando-os entre múltiplos processos.

#### Funções do SO
- **Gerenciador de Recursos**: Responsável pelo hardware e gerenciamento de acesso às suas partes.
- **Provedor de Serviços**: Fornece uma abstração de baixo nível para aplicações.
- **Máquina Virtual**: Oferece uma ilusão de que uma aplicação está executando sozinha no hardware.

### Responsabilidades do SO

#### Áreas de Responsabilidade
- **Processos**:
  - Execução de programas na CPU.
  - Serviços de suporte incluem criação, destruição, escalonamento, e comunicação entre processos.

- **Memória**:
  - Gerenciamento do espaço de memória.
  - Prevenção de interferência entre processos.
  - Serviços de alocação e liberação de memória.

- **Dispositivos de E/S**:
  - Facilitação da comunicação com dispositivos.
  - Gerenciamento de acesso e exclusividade de dispositivos.

- **Sistema de Arquivos**:
  - Armazenamento e recuperação de dados persistentes.
  - Operações de abrir, fechar, ler, e escrever arquivos.

- **Segurança**:
  - Controle de acesso a recursos do sistema.
  - Implementação de políticas de segurança e autenticação.

- **Redes**:
  - Implementação de pilhas de protocolos.
  - Gerenciamento de conexões de rede.

- **Interface com o Usuário**:
  - Interação do usuário com o sistema através de interfaces como terminais de comando e gerenciadores de tarefas.

### Organização de Sistemas Operacionais

#### Modelos
- **Modelos Monolíticos**:
  - Sistema organizado como um único programa.
  - Falta de organização estrutural.

- **Modelos em Camadas**:
  - Organização em pilhas de camadas, aumentando a abstração em cada nível.

- **Modelos de Microkernel**:
  - Redução das funções do kernel para processos menores e mais eficientes.
  - Comunicação via troca de mensagens.

- **Modelos de Máquina Virtual**:
  - Proporciona a ilusão de múltiplas cópias de hardware.
  - Permite a execução de mais de um SO sobre o mesmo hardware.

### Bootstrapping

#### Processo de Inicialização
- **Bootstrapping**:
  - Transição do hardware puro para um SO em execução.
  - Conhecido também como partida a frio ou Initial Program Load (IPL).

#### Abordagens de Bootstrapping
- **Painel Frontal**: Configuração manual de memória e CPU.
- **Programa de Bootstrap**: Executado a partir de mídia como cartões perfurados.
- **Memória ROM**: Uso de firmware armazenado em ROM.

#### Sistemas Atuais
- **Firmware**: Programa essencial para funcionamento do hardware.
  - **BIOS**: Basic Input/Output System, em desuso.
  - **UEFI**: Substitui BIOS, compatível com 32 e 64 bits, não dependente de ROM.

### Chamadas ao Sistema

#### Definição
- **Chamadas ao Sistema (System Calls)**:
  - Mecanismo para solicitações de serviços do SO por processos.
  - Proveem interfaces escritas em linguagens como C e C++.

## Gerenciamento de Memória

### Introdução

O gerenciamento de memória é uma das funções mais críticas de um sistema operacional, responsável por alocar e gerenciar eficientemente a memória disponível para os processos em execução. Este tópico abrange desde a simples alocação de memória até técnicas avançadas como segmentação e memória virtual.

### Sistema de Endereçamento de Memória

#### Definição
- **Sistema de Endereçamento de Memória**: Mecanismo que define como os endereços de memória são interpretados e acessados pelo sistema operacional e pelas aplicações. Ele determina a forma como os processos referenciam a memória e como o SO mapeia esses endereços para a memória física.

### Abstração de Memória

#### Conceito
- **Abstração de Memória**: Técnica que permite que cada processo tenha seu próprio espaço de endereçamento independente, facilitando a proteção e a relocação.
  - **Proteção**: Garantia de que um processo não pode acessar a memória de outro processo, prevenindo interferências e garantindo a integridade dos dados.
  - **Relocação**: Capacidade de mover processos na memória física sem alterar os endereços virtuais, aumentando a flexibilidade na alocação de memória.

### Memória Virtual

#### Definição
- **Memória Virtual**: Técnica que combina a memória principal (RAM) com a memória secundária (disco) para simular uma memória maior do que a fisicamente disponível.
  - **Espaço de Endereçamento Virtual**: Cada processo possui seu próprio espaço de endereçamento virtual, dividido em páginas.
  - **MMU (Memory Management Unit)**: Unidade responsável pelo mapeamento de endereços virtuais para endereços físicos, garantindo que os processos acessem apenas as áreas de memória permitidas.

#### Funcionamento
A memória virtual permite que programas maiores do que a memória física sejam executados, dividindo-os em blocos chamados páginas. Essas páginas podem ser carregadas e descarregadas conforme a necessidade, permitindo um uso mais eficiente da memória disponível.

### Algoritmos de Substituição de Páginas

#### Definição
- **Algoritmos de Substituição de Páginas**: Políticas utilizadas pelo SO para decidir qual página da memória deve ser removida quando uma nova página precisa ser carregada.

#### Principais Algoritmos
1. **FIFO (First In, First Out)**
   - **Funcionamento**: Substitui a página que está na memória há mais tempo.
   - **Vantagens**: Fácil de implementar.
   - **Desvantagens**: Pode levar à anomalia de Belady, onde aumentar o número de frames pode aumentar o número de faltas de página.

2. **LRU (Least Recently Used)**
   - **Funcionamento**: Substitui a página que não foi usada recentemente.
   - **Vantagens**: Aproximação eficiente do algoritmo ótimo, respeita o princípio da localidade de referência.
   - **Desvantagens**: Difícil de implementar devido à necessidade de rastrear os acessos recentes a todas as páginas.

3. **OPT (Ótimo)**
   - **Funcionamento**: Substitui a página que não será usada por mais tempo no futuro.
   - **Vantagens**: Minimiza o número de faltas de página.
   - **Desvantagens**: Não é implementável na prática, pois requer conhecimento do comportamento futuro.

4. **Algoritmo da Segunda Chance (Clock)**
   - **Funcionamento**: Variante do FIFO que dá uma segunda chance às páginas que foram recentemente referenciadas.
   - **Vantagens**: Melhora o desempenho do FIFO, evitando a remoção de páginas recentemente usadas.
   - **Desvantagens**: Ainda pode sofrer com algumas ineficiências dependendo do padrão de acesso.

5. **NRU (Not Recently Used)**
   - **Funcionamento**: Classifica as páginas com base em bits de referência (R) e modificação (M) e prefere substituir páginas das classes com menor prioridade.
   - **Classes**:
     - **Classe 0**: R = 0, M = 0
     - **Classe 1**: R = 0, M = 1
     - **Classe 2**: R = 1, M = 0
     - **Classe 3**: R = 1, M = 1

6. **Algoritmo do Envelhecimento**
   - **Funcionamento**: Utiliza contadores para rastrear a frequência e a recência dos acessos às páginas.
   - **Mecanismo**: Desloca o contador para a direita e adiciona o bit de referência no bit mais significativo periodicamente.
   - **Vantagens**: Diferencia acessos recentes dos antigos, evitando overflow dos contadores.
   - **Desvantagens**: Implementação mais complexa devido à necessidade de manutenção dos contadores.

### Segmentação

#### Definição
- **Segmentação**: Técnica que divide o espaço de endereçamento de um processo em segmentos lógicos de tamanhos variáveis, como código, dados e pilha.
  - **Segmentação Pura**: Cada segmento é uma sequência linear de endereços de 0 até um tamanho máximo, permitindo tamanhos variáveis para diferentes segmentos.
    - **Vantagens**: Facilita a organização lógica dos programas.
    - **Desvantagens**: Pode levar à fragmentação externa devido aos tamanhos variáveis dos segmentos.

#### Segmentação com Paginação
- **Definição**: Combinação de segmentação e paginação, dividindo cada segmento em páginas de tamanho fixo.
  - **Vantagens**: Reduz a fragmentação externa da segmentação pura e facilita a gestão de memória.
  - **Desvantagens**: Adiciona complexidade na gestão das tabelas de segmentos e páginas.

#### Implementação no MULTICS
- **Características**:
  - **Número de Segmentos**: Mais de 250 mil segmentos.
  - **Tamanho dos Segmentos**: Cada segmento pode ter até 65.536 (36 bits) palavras.
  - **Tabela de Segmentos**: Cada programa possui uma tabela de segmentos com descritores para cada segmento.
  - **Descritor de Segmento**: Contém informações como endereço base, tamanho e permissões de acesso.
  - **Conversão de Endereços**: A MMU utiliza os descritores de segmentos para mapear endereços virtuais para físicos, garantindo proteção e relocação.
  - **Tabela de Segmentos Ocupa um Segmento**: Devido ao seu tamanho, a tabela de segmentos pode ocupar um segmento inteiro.

### Objetivos do Gerenciamento de Memória

- **Manter o Maior Número Possível de Processos em Memória**: Maximizar a utilização da memória disponível para aumentar o throughput do sistema.
- **Maximizar o Compartilhamento de Espaço de Memória**: Permitir que múltiplos processos compartilhem partes da memória sem interferência.
- **Executar Programas com Requisitos de Memória Além da Capacidade Física da RAM**: Utilizar memória virtual para suportar grandes aplicações que excedem a memória física.
- **Proteger as Áreas de Memória Ocupadas por Cada Processo**: Garantir que processos não acessem ou modifiquem a memória de outros processos, assegurando a integridade e a segurança dos dados.

### Contexto

#### Hierarquia de Memória
- **Registradores**: Memória de alta velocidade dentro da CPU, usada para operações imediatas.
- **Cache**: Memória intermediária rápida entre a CPU e a RAM, utilizada para armazenar dados acessados frequentemente.
- **Memória Principal (RAM)**: Memória volátil usada para armazenar dados e programas em execução.
- **Armazenamento Secundário**: Dispositivos não voláteis como discos rígidos (HDD) e unidades de estado sólido (SSD).
- **Armazenamento Permanente**: Memória que mantém dados mesmo quando o sistema está desligado, como CDs, DVDs e pen drives.

#### Estratégias de Gerenciamento
- **Busca**: Determinar quando transferir processos ou partes deles para a RAM.
- **Posicionamento**: Decidir onde na RAM alocar novos processos ou suas partes.
- **Substituição**: Escolher quais processos ou partes deles devem ser removidos da memória para liberar espaço.
- **Endereçamento**: Garantir que os endereços virtuais sejam corretamente mapeados para endereços físicos, fundamental para todas as estratégias anteriores.

### Estratégias de Gerenciamento de Memória

#### Espaços de Endereçamento
- **Espaços de Endereçamento**: Cada processo possui um conjunto de endereços que pode usar para acessar a memória, definidos de forma independente.
- **Relocação Dinâmica**: Mapeamento de cada endereço virtual para uma localização diferente na memória física durante a execução.
- **Registrador-Base e Registrador-Limite**: Utilizados para definir o início e o fim do espaço de endereçamento de um processo, garantindo que ele não acesse áreas não autorizadas.

#### Swapping (Troca de Processos)
- **Definição**: Técnica de mover processos entre a memória principal e a memória secundária para liberar espaço.
- **Funcionamento**: Quando a memória principal está cheia, o SO escolhe processos menos ativos para serem movidos para a memória secundária, liberando espaço para novos processos.
- **Compactação de Memória**: Combinação de espaços vazios na memória para criar um espaço contíguo maior, facilitando a alocação de novos processos.
  - **Problema**: Processo lento devido ao tempo necessário para copiar grandes blocos de memória.
  - **Solução**: Estender a memória utilizando técnicas como swapping para minimizar a necessidade de compactação frequente.

#### Gerenciamento de Memória Livre
- **Mapa de Bits**
  - **Definição**: Representação da memória livre e ocupada usando bits, onde cada bit indica se uma unidade de alocação está livre ou ocupada.
  - **Vantagens**: Simplicidade na verificação de espaços livres.
  - **Desvantagens**: Pode ser ineficiente na busca por espaços contíguos grandes, especialmente com unidades de alocação pequenas.

- **Listas Encadeadas**
  - **Definição**: Estrutura que mantém uma lista de segmentos de memória livres e alocados, ordenados por endereço.
  - **Vantagens**: Facilita a alocação e desalocação de blocos de memória de diferentes tamanhos.
  - **Desvantagens**: Pode ser mais complexa de implementar e gerenciar do que mapas de bits.

- **Algoritmos de Alocação**
  1. **Best Fit**
     - **Definição**: Aloca a menor área livre que seja suficiente para o processo.
     - **Vantagens**: Minimiza o desperdício de memória.
     - **Desvantagens**: Pode levar a fragmentação interna e aumentar o tempo de busca.

  2. **Worst Fit**
     - **Definição**: Aloca a maior área livre disponível.
     - **Vantagens**: Reduz o número de fragmentos pequenos.
     - **Desvantagens**: Pode desperdiçar grandes áreas de memória.

  3. **First Fit**
     - **Definição**: Aloca a primeira área livre que seja suficiente.
     - **Vantagens**: Rápido na alocação.
     - **Desvantagens**: Pode levar à fragmentação inicial da memória.

### Paginação

#### Memória Virtual
- **Divisão em Páginas e Frames**
  - **Páginas**: Unidades de memória virtual de tamanho fixo, por exemplo, 4KB.
  - **Frames**: Blocos de memória física de tamanho correspondente às páginas.
  - **Transferências por Páginas**: Movimentação de páginas inteiras entre a memória principal e a memória secundária.

#### Tabela de Páginas
- **Definição**: Estrutura de dados que mantém o mapeamento de páginas virtuais para frames físicos.
- **Entrada da Tabela de Páginas**: Contém informações como o endereço do frame, bits de presença (present/absent), referência (R) e modificação (M).

#### Mapeamento de Páginas
- **Conversão de Endereços**
  - **Processo**: A MMU utiliza a tabela de páginas para converter endereços virtuais em físicos.
  - **Exemplo de Mapeamento**:
    - **Endereço Virtual 8192**: Página virtual 2 mapeada para frame 6 → Endereço Físico 24576.
    - **Endereço Virtual 20500**: Página virtual 5 com deslocamento de 20 bytes mapeada para frame 3 → Endereço Físico 12308.

#### Faltas de Página
- **Definição**: Ocorrência quando um processo tenta acessar uma página que não está presente na memória física.
- **Processo**:
  1. **Interrupção**: A MMU gera uma interrupção para sinalizar a falta de página.
  2. **Escolha da Página a Ser Removida**: O SO escolhe uma página a ser removida da memória para liberar espaço.
  3. **Atualização**: Se a página a ser removida foi modificada, ela é salva de volta na memória secundária.
  4. **Carregamento da Nova Página**: A página solicitada é carregada da memória secundária para a memória principal.

### Algoritmos de Substituição de Páginas

#### FIFO (First In, First Out)
- **Funcionamento**: Substitui a página que está na memória há mais tempo.
- **Vantagens**: Fácil de implementar.
- **Desvantagens**: Pode levar à anomalia de Belady, onde aumentar o número de frames pode aumentar o número de faltas de página.

#### OPT (Ótimo)
- **Funcionamento**: Substitui a página que não será usada por mais tempo no futuro.
- **Vantagens**: Minimiza o número de faltas de página.
- **Desvantagens**: Não é implementável na prática, pois requer conhecimento do comportamento futuro.
- **Utilidade**: Serve como uma referência teórica para avaliar o desempenho de outros algoritmos.

#### LRU (Least Recently Used)
- **Funcionamento**: Substitui a página que não foi usada recentemente.
- **Vantagens**: Aproximação eficiente do algoritmo ótimo, respeita o princípio da localidade de referência.
- **Desvantagens**: Difícil de implementar devido à necessidade de rastrear os acessos recentes a todas as páginas.
- **Exemplo**:
  - **Cadeia de Referência**: 0; 2; 1; 3; 5; 4; 6; 3; 7; 4; 7; 3; 3; 5; 5; 3; 1; 1; 1; 7; 1; 3; 4; 1
  - **Memória com 3 Frames**:
    - As páginas são substituídas com base no último acesso, removendo a que foi menos recentemente usada.

#### Algoritmo da Segunda Chance (Clock)
- **Funcionamento**: Variante do FIFO que dá uma segunda chance às páginas que foram recentemente referenciadas.
- **Mecanismo**:
  1. **Fila Circular**: Utiliza uma fila circular para manter a ordem das páginas.
  2. **Bit de Referência**: Cada página possui um bit de referência que indica se foi acessada recentemente.
  3. **Processo de Substituição**:
     - A página na frente da fila é verificada.
     - Se o bit de referência estiver setado (1), ele é resetado e a página é movida para o final da fila.
     - Se o bit de referência estiver resetado (0), a página é substituída.
- **Vantagens**: Melhora o desempenho do FIFO, evitando a remoção de páginas recentemente usadas.

#### NRU (Not Recently Used)
- **Funcionamento**: Classifica as páginas com base em bits de referência (R) e modificação (M) e prefere substituir páginas das classes com menor prioridade.
- **Classes**:
  - **Classe 0**: R = 0, M = 0
  - **Classe 1**: R = 0, M = 1
  - **Classe 2**: R = 1, M = 0
  - **Classe 3**: R = 1, M = 1
- **Mecanismo**: Prefere substituir páginas das classes 0 e 1 antes de considerar as classes 2 e 3.

#### Algoritmo do Envelhecimento
- **Funcionamento**: Utiliza contadores para rastrear a frequência e a recência dos acessos às páginas.
- **Mecanismo**:
  1. **Contadores**: Cada página possui um contador de N bits.
  2. **Atualização Periódica**: Periodicamente, os contadores são deslocados para a direita e o bit de referência é inserido no bit mais significativo.
  3. **Substituição**: A página com o menor valor no contador é substituída, indicando que foi menos recentemente usada.
- **Vantagens**: Diferencia acessos recentes dos antigos, evitando overflow dos contadores.
- **Desvantagens**: Implementação mais complexa devido à necessidade de manutenção dos contadores.

### Implementação de Segmentação

#### Segmentação Pura
- **Definição**: Divide o espaço de endereçamento em segmentos lógicos de tamanhos variáveis, como código, dados e pilha.
- **Endereçamento**: Utiliza um par (número do segmento, deslocamento) para acessar a memória.
- **Vantagens**: Facilita a organização lógica dos programas, permitindo tamanhos variáveis para diferentes segmentos.
- **Desvantagens**: Pode levar à fragmentação externa devido aos tamanhos variáveis dos segmentos.

#### Segmentação com Paginação
- **Definição**: Combina segmentação e paginação, dividindo cada segmento em páginas de tamanho fixo.
- **Vantagens**: Reduz a fragmentação externa da segmentação pura e facilita a gestão de memória.
- **Desvantagens**: Adiciona complexidade na gestão das tabelas de segmentos e páginas.

#### Implementação no MULTICS
- **Características**:
  - **Número de Segmentos**: Mais de 250 mil segmentos.
  - **Tamanho dos Segmentos**: Cada segmento pode ter até 65.536 (36 bits) palavras.
  - **Tabela de Segmentos**: Cada programa possui uma tabela de segmentos com descritores para cada segmento.
  - **Descritor de Segmento**: Contém informações como endereço base, tamanho e permissões de acesso.
  - **Conversão de Endereços**: A MMU utiliza os descritores de segmentos para mapear endereços virtuais para físicos, garantindo proteção e relocação.
  - **Tabela de Segmentos Ocupa um Segmento**: Devido ao seu tamanho, a tabela de segmentos pode ocupar um segmento inteiro.

### Resumo

- **Gerenciamento de Memória**: Essencial para a eficiência e segurança dos sistemas operacionais, permitindo a execução de múltiplos processos de forma eficiente.
- **Memória Virtual e Paginação**: Permitem a execução de programas maiores que a memória física e facilitam o compartilhamento de memória entre processos.
- **Algoritmos de Substituição de Páginas**: Influenciam diretamente o desempenho do sistema ao gerenciar quais páginas permanecem na memória.
- **Segmentação**: Oferece uma abordagem lógica para a gestão de memória, alinhando-se com a estrutura dos programas e reduzindo a fragmentação.
- **Implementação Avançada (MULTICS)**: Demonstra técnicas sofisticadas de segmentação e paginação para otimizar o uso da memória em sistemas complexos.

