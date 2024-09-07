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

## Fundamentos de Gerenciamento de Processos

### 1. Conceito de Processos

- **Processo:** Programa em execução; necessário para a concorrência de programas pelo sistema operacional.
- **Partes de um Processo:**
  - **Contexto de Hardware:** Contém o conteúdo dos registradores da CPU.
  - **Contexto de Software:** Limites e características dos recursos alocados, como número máximo de arquivos e tamanho do buffer.
  - **Espaço de Endereçamento:** Área de memória do processo para instruções e dados.
- **Operações sobre Processos:**
  - Criar, terminar, mudar programa, definir parâmetros, obter parâmetros, bloquear, despertar, trocar e escalonar processos.

### 2. Estrutura de Processos

- **Tabela de Processos (PCB):** Representa o processo no SO; contém informações sobre o estado do processo, contador do programa, registradores de CPU, etc.
- **Estados de um Processo:**
  - **Executando:** Processo está ativo na CPU.
  - **Pronto:** Aguardando na fila para ser executado.
  - **Bloqueado:** Aguardando um evento externo.

### 3. Threads

- **Conceito de Threads:** Múltiplos controles de execução dentro de um mesmo processo, compartilhando o mesmo espaço de endereçamento e recursos.
- **Vantagens:**
  - Elimina a troca de contexto entre processos.
  - Mais rápidas e econômicas em termos de recursos do sistema.
  - Melhor desempenho em sistemas com múltiplas CPUs.
- **Modelos de Threads:**
  - **Modelo Clássico:** Threads compartilham o mesmo espaço de endereçamento e recursos, mas têm pilhas próprias.

### 4. Implementação de Threads

- **Modo Usuário:**
  - Threads são gerenciadas em nível de usuário, não requerendo suporte do kernel.
  - Vantagens: Alternância rápida de threads; menos chamadas ao kernel.
  - Desvantagens: Limitações em sistemas sem suporte para threads.

- **Modo Kernel:**
  - Threads são gerenciadas diretamente pelo kernel.
  - Vantagens: Threads não bloqueiam o processo inteiro.
  - Desvantagens: Mais caro devido às chamadas de sistema.

## Escalonamento de Processos

### O que é Escalonamento de Processos?

- **Definição:**  
  Mecanismo usado pelo Sistema Operacional (SO) para selecionar qual processo obterá a CPU.

- **Função do Escalonador:**  
  O Escalonador utiliza algoritmos de escalonamento para selecionar processos seguindo diversos critérios.

### Comportamento do Processo

- **Tipos de Limitação:**  
  - Limitados pela CPU – *CPU-bound*
  - Limitados pela E/S – *I/O-bound*

- **Interações com o Sistema:**  
  - Processos na CPU intercalam suas ações entre processamento e chamadas ao sistema.
  - Quando ocorrem chamadas ao sistema, o processo é bloqueado e o sistema assume para executar a chamada.

### Quando Escalonar?

- Quando um processo é criado.
- Quando um processo finaliza.
- Quando um processo bloqueia.
- Quando ocorre interrupção de E/S.

## Propósitos e Princípios de Escalonamento

### Objetivos do Escalonamento

- Manter a CPU ocupada a maior parte do tempo.
- Balancear o uso da CPU entre processos.
- Privilegiar a execução de aplicações críticas.
- Maximizar o throughput.
- Oferecer tempos de resposta razoáveis para usuários interativos.

### Princípios de Todos os Sistemas Operacionais

- **Justiça:** Porção justa de CPU para cada processo.
- **Aplicação da Política:** Cumprimento da política é essencial.
- **Equilíbrio:** Manter ocupadas todas as partes do sistema.

### Escolha do Processo

- Os princípios que regem a escolha do processo compõem a política de escalonamento de acordo com o tipo de SO.

## Políticas de Escalonamento

### Tipos de Sistemas

#### Sistemas em Lote

- **Vazão (Throughput):** Maximizar o número de tarefas por unidade de tempo.
- **Tempo de Retorno:** Reduzir o tempo entre a submissão e a conclusão.
- **Utilização de CPU:** Manter a CPU ocupada o tempo todo.

#### Sistemas Interativos

- **Tempo de Resposta:** Responder rapidamente às requisições.
- **Proporcionalidade:** Satisfazer as expectativas do usuário.

#### Sistemas de Tempo Real

- **Cumprimento do Prazo:** Evitar perda de dados.
- **Previsibilidade:** Evitar degradação da qualidade de sistemas multimídia.

### Políticas de Escalonamento Não-Preemptivas

- **Definição:**  
  Os sistemas operacionais confiavam que os processos devolveriam o controle da CPU voluntariamente.

- **Problema:**  
  Ao longo do tempo, essa abordagem se mostrou ineficiente.

### Políticas de Escalonamento Preemptivas

- **Preemptiva:**  
  Permite que o SO interrompa um processo a qualquer instante para executar outro processo (chaveamento de contexto).

- **Não-Preemptiva:**  
  Permite que o processo execute até concluir, ser bloqueado ou voluntariamente entregar o processador ao SO.

### Quanto à Prioridade do Processo

- **Prioridade Estática:**  
  A prioridade é definida em tempo de implantação do processo.

- **Prioridade Dinâmica:**  
  A prioridade é definida em tempo de execução do processo.

- **Inversão de Prioridade:**  
  O SO aumenta a prioridade para que o processo finalize e libere recursos.
    
### Sistemas Operacionais Modernos

- Os algoritmos combinam dois ou mais critérios e são adaptativos.

## Algoritmos de Escalonamento

### Algoritmos Não-Preemptivos

#### FCFS (First Come, First Served)

- **Definição:**  
  Fila simples - O primeiro a entrar será o primeiro a ser executado.

- **Vantagens:**  
  - Justo no sentido de atender segundo ordem de chegada.
  - Não permite a ocorrência de adiamento indefinido.
  - Fácil de implementar.
  - Apropriado para sistemas em lote.

- **Desvantagens:**  
  - Processos longos fazem os curtos esperarem muito.
  - Não se mostra eficiente para processos interativos.
  - Não considera a importância de uma tarefa.

- **Desempenho:**  
  Existe diferença no desempenho a ordem de chegada dos processos?

#### SJF (Shortest Job First)

- **Definição:**  
  Fila ordenada conforme o tempo de execução.

- **Ordenação:**  
  Ordenação crescente: menores primeiro.

- **Vantagens:**  
  - Favorece os processos mais curtos.
  - Apropriado para sistemas em lote.

- **Desvantagens:**  
  - Necessário saber, a priori, o tempo de execução do processo.
  - Pode causar adiamento indefinido.

## Algoritmos Preemptivos

### Algoritmo RR (Round Robin)

- **Definição:**  
  Escalonamento Preemptivo.

- **Mecanismo:**  
  Fila circular – cada processo tem uma “fatia de tempo” (quantum ou time-slice) para usar o processador – tempo compartilhado.

- **Preempção por Tempo:**  
  Interrupção de um processo em execução quando a sua fatia de tempo expira.


## Algoritmo de Múltiplas Filas

### Definição

- **Escalonamento Preemptivo:**  
  Diversas filas de processos no estado pronto.

- **Prioridade:**  
  Cada fila tem uma prioridade.

- **Definição de Prioridade:**  
  Prioridade definida pelas propriedades do processo:
  - Tamanho da memória.
  - Tipo de processo.

- **Algoritmos:**  
  Cada fila tem seu próprio algoritmo de escalonamento.

- **Mecanismo:**  
  - Sempre que um processo chega na fila de maior prioridade, o processo em execução sofre preempção, caso seja de uma fila com prioridade menor.
  - Só se pode escalonar um processo de uma determinada fila caso as filas de maior prioridade estejam vazias.

### Vantagens

- Permite mecanismos de escalonamento distintos em um único SO.

### Desvantagens

- Mesmo que um processo mude seu comportamento, ele não poderá mudar de fila.

## Algoritmo de Múltiplas Filas com Realimentação

### Escalonamento por Preempção

- **Mecanismo de Ajuste Dinâmico:**  
  Baseado no comportamento do processo.

- **Comportamento do Processo:**  
  - Processos iniciam sempre na fila 0: maior prioridade, menos tempo.
  - Processos *I/O-bound* e processos interativos sempre ficam nas filas de maior prioridade.
  - Um processo velho (há muito tempo na fila) pode ser deslocado para uma fila de maior prioridade.

## Escalonamento no UNIX

### Caso de Uso

- **Unix:**  
  É um SO multiprogramado de tempo compartilhado.

- **Meta:**  
  Bom tempo de resposta aos processos interativos.

### Escalonamento de 2 Níveis

- **Escalonador de Baixo Nível:**  
  Filas Múltiplas (prioridade) com realimentação.

- **Modo Kernel:**  
  - Processos executando em modo kernel: prioridade negativa (que são as maiores).
  - Processos executando em modo usuário: prioridade positiva.

- **Processo de Escalonamento:**  
  - Roda primeiro processo da fila prioritária não vazia.
  - Interrupções de tempo: incremento do contador de utilização da CPU (que aumentará o valor da prioridade do processo).
  - Escalonamento circular dentro de cada fila.
  - A cada segundo as prioridades são recalculadas.
  - Processos interativos voltam do bloqueio com prioridade negativa.

# Capítulo 3: Gerenciamento de Memória

## Introdução
- **Contexto Histórico:** Os computadores modernos têm muito mais memória do que os primeiros computadores, como o IBM 7094.
- **Problema:** Os programas estão crescendo mais rapidamente do que a capacidade de memória disponível, consumindo recursos conforme disponíveis.

## Desejo Ideal e Realidade Tecnológica
- **Ideal:** Memória privada, infinita, rápida e não volátil.
- **Realidade:** Ainda não existem tecnologias que ofereçam tais memórias a um custo viável.

## Hierarquia de Memórias
- **Estrutura:** Composta por memória cache (rápida, volátil, cara), memória principal (velocidade e custo médios), e armazenamento em disco (barato, não volátil, lento).
- **Função do SO:** Abstrair e gerenciar essa hierarquia.

## Gerenciamento de Memória
- **Gerenciador de Memória:** Parte do sistema operacional responsável por controlar e alocar a memória.

## Modelos de Gerenciamento de Memória
- **De simples a sofisticados:** Abordagem gradual sobre diferentes esquemas de gerenciamento.

### Sem Abstração de Memória
- **Antigamente:** Computadores sem abstração de memória, onde programas acessavam a memória física diretamente.
- **Desvantagens:** Impossibilidade de executar múltiplos programas simultaneamente sem interferências.

### Com Abstração de Memória
- **Espaços de Endereçamento:** Criação de um conjunto de endereços que um processo pode usar, separado de outros processos.
- **Benefícios:** Proteção e isolamento entre processos, permitindo a execução simultânea de múltiplos programas.

## Implementações Técnicas
- **Registradores Base e Limite:** Usados para mapear o espaço de endereçamento de um processo para a memória física.
- **Hardware Especial:** IBM 360 utilizou chaves de proteção para evitar que processos acessassem memórias de outros processos.

## Desafios e Soluções
- **Swapping:** Técnica de salvar o estado de um processo em disco e carregar outro, permitindo a alternância entre programas.
- **Realocação Estática e Dinâmica:** Ajustes nos programas durante o carregamento para ajustar referências de memória.
