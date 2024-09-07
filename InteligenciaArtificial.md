# Inteligência Artificial

### Conceitos Fundamentais
- **Dado**: Registro de valores sem semântica (ex.: João de Deus; 45).
- **Informação**: Valores com semântica (ex.: Rua: João de Deus; 45).
- **Conhecimento**: Análise das informações para produzir novos insights.
- **Inteligência**: Processo de criação de conhecimento.
- **Ação**: Uso do conhecimento para modificar o ambiente.

### Tipos de Conhecimento
- **Explícito**: Articulado em linguagem formal, fácil de transmitir.
- **Tácito**: Subjetivo, baseado em experiência, difícil de formalizar.

## Objetivo da IA
Estudo e modelagem da inteligência para entender e imitar a mente humana.

### Questões-Chave
- Como ocorre o pensamento?
- Como extraímos conhecimento do mundo?
- Como surgem ideias e decisões?

### Abordagens da IA
- **Cognitiva**: Explica comportamentos inteligentes com base em psicologia e lógica.
- **Conexionista**: Imita o cérebro e conexões neurais, sem explicar o comportamento.

## Algoritmos Genéticos

### Introdução
- Inspirados na Seleção Natural de Darwin.
- Criam populações de indivíduos (cromossomos) que evoluem.
- Usado em problemas onde não é viável testar todas as soluções (ex.: problemas NP-difíceis).

### Onde usar?
- Quando o objetivo é encontrar uma das melhores soluções, não a solução ótima.
- Quando é possível criar uma função de avaliação para as soluções.
- Quando é possível gerar respostas mecanicamente (com ou sem heurística).

### Analogias
| Darwin                  | Algoritmos Genéticos                      |
|-------------------------|-------------------------------------------|
| Meio ambiente           | Domínio do problema                       |
| Indivíduos              | Soluções válidas                          |
| Atributos dos indivíduos| Valores para avaliação                    |
| Os mais aptos           | Soluções de alta qualidade                |
| Cruzamentos             | Combinações de soluções                   |
| Mutação                 | Alteração aleatória em soluções           |

### Algoritmo Geral
1. **População Inicial**: Criada aleatoriamente, representando o universo de soluções.
2. **Cálculo da Aptidão**: Avaliação da qualidade das soluções.
3. **Seleção Natural**: Seleção dos melhores indivíduos.
4. **Reprodução e Mutação**: Combinação e alteração de atributos para gerar nova população.

### População Inicial
- Amostra heterogênea e diversa do universo de soluções.
- Criada aleatoriamente, mas apenas com soluções válidas.
- Heurísticas podem ser usadas para eliminar soluções ruins.

### Cálculo da Aptidão
- Função de avaliação geral para as soluções.
- Considerar normalização e pesos para atributos.
- Combinação de funções e métricas independentes.

### Critérios de Parada
- Se o melhor indivíduo atingiu qualidade aceitável.
- Se a evolução parou ao longo das gerações.
- Número máximo de iterações para evitar loops infinitos.

### “Seleção Natural”
- Seleção dos melhores indivíduos (N) para a próxima geração.
- Garantir que os pais selecionados estejam na próxima geração para evitar retrocesso.

### Reprodução e Mutação
- **Reprodução**: Cruzamento de genes (atributos) dos pais, com pontos de corte aleatórios.
- **Mutação**: Alteração aleatória para evitar máximos locais.

### Problemas Tradicionais para AG
- Caixeiro Viajante
- Otimização de agenda
- Elaboração de projetos complexos
- Otimização de escalas e grades de horários
- Simulações de comportamento

## Lógica Fuzzy
- **Criada por Lofti Zadeh (década de 60)**, popularizada nos anos 80, no Japão.
- Representa a **imprecisão e incerteza** em informações.

### Comparação de Lógicas
- **Lógica Booleana**: Verdadeiro/Falso, não tolera incerteza.
- **Lógica Multi-valorada**: Ex. L3, estados: Verdadeiro, Falso, “Meio”.
- **Lógica Fuzzy**: Quantifica o grau de incerteza com valores entre [0..1].

### Conceitos de Grau
- **Grau de Crença (Probabilidade)**: Ex. 80% de pacientes com dor de dente têm cáries.
- **Grau de Verdade (Lógica Fuzzy)**: Ex. "Mario é alto" (interpretável para 1.65m).

### Aplicação de Lógica Fuzzy
- **Exemplo**: Definição de idade (jovem, adulto, idoso) é tratada de forma mais flexível que na lógica booleana.

### Processo de Inferência Fuzzy
1. **Fuzzificação**: Converte variáveis precisas em nebulosas.
2. **Inferência**: Aplicação de regras nebulosas.
3. **Defuzzificação**: Converte variáveis nebulosas de volta para precisas.

### Operadores Fuzzy
- **Interseção**: Min(μA(x), μB(x))
- **União**: Max(μA(x), μB(x))
- **Complemento**: 1 - μA(x)

## Aplicações de Lógica Fuzzy
- **Mitsubishi**: Ar condicionado com controlador fuzzy (economiza 24% de energia).
- **Metrô de Sendai, Japão**: Controlador fuzzy para suavizar viagens.
- **Câmeras/Gravadoras**: Ajuste automático de foco e cancelamento de tremores.
- **Nissan**: Sistemas de freio, controle de transmissão, injetores de combustível fuzzy.
- **Software**: Busca e comparação de imagens.

## Compreendendo os Sistemas Especialistas

### Definição
- **Sistemas Especialistas (SE)**: Sistemas que empregam raciocínio lógico dedutivo e o conhecimento humano para resolver problemas que exigem um especialista.

### Utilidade
- Capacitar/ajudar não-especialistas.
- Servir como repositório de conhecimento valioso para a empresa.

### Visão Geral de um SE
- **Máquina de Inferência**: Executa o raciocínio lógico.
- **Base de Conhecimento**: Contém as regras fornecidas pelo especialista.
- **Memória de Trabalho**: Armazena fatos, hipóteses e decisões.

### Representação do Conhecimento
- **Regras de Produção**: Fórmulas lógicas que representam variáveis ou características.
- Podem ser usadas lógicas fuzzy, redes semânticas, etc.

### Processo de Inferência
1. **Memória de Trabalho**: Registra descrição do problema, hipóteses, sub-objetivos, etc.
2. **Máquina de Inferência**:
   - Interpretador: Unifica, casa e executa regras.
   - Controlador de Agenda: Ordena ações segundo estratégias.
   - Verificador de Consistência: Assegura a validade das inferências.

### Métodos de Raciocínio
- **Encadeamento para frente** (forward chaining).
- **Encadeamento para trás** (backward chaining).

### Engenheiro de Conhecimento
- **Responsabilidades**:
   - Extrair conhecimento do especialista.
   - Representar esse conhecimento na base de conhecimento.
- **Problemas Potenciais**:
   - Conhecimento pode ser incompleto, irrelevante ou incorreto.

### Grau de Certeza (FC)
- **Fator de Confiança (FC)**: Associa um grau de certeza às conclusões do SE.

### Cálculo do FC
- **Operador 'E'**: Multiplicação dos graus de confiança.
- **Operador 'OU'**: FC = FC1 + FC2 - FC1 * FC2.
- Quando múltiplas regras suportam uma conclusão, combinam-se os fatores de confiança.

### Exemplo de FC
- **Fatos na Memória de Trabalho**:
   - trabalhou_muito CF = 90
   - dor_de_cabeça CF = 100
- **Regras**:
   - IF trabalhou_muito THEN precisa_dormir CF = 50
   - IF dor_de_cabeça THEN precisa_dormir CF = 50
- **Resultado**:
   - CF final de precisa_dormir = 72,5

## Raciocínio Baseado em Casos (RBC)

### RBC e Experiência
- **Experiência**: Conhecimento explícito absorvido e transformado em conhecimento tácito.
- **Exemplo**: Estudante de medicina desenvolve experiência até se tornar um médico especialista, capaz de resolver problemas com maior eficiência.

### Definição de “caso”
- **Kolodner (1993)**: "Um pedaço contextualizado de conhecimento representando uma experiência que ensina uma lição fundamental para resolver um problema."
- **Componentes de um caso**:
  - Descrição do problema
  - Solução ou conjunto de ações para o problema
  - Avaliação da solução

### O que é Raciocínio Baseado em Casos?
- Técnica que busca soluções baseadas na experiência de casos anteriores para resolver novos problemas.
- **Questões-chave**:
  - Como armazenar os casos?
  - Como tratar a métrica de similaridade?
  - Qual será o algoritmo de adaptação para novas soluções?
  - Estratégias para aquisição de novos casos?

### Quando utilizar RBC?
- Existe um volume de dados históricos ou há uma fase inicial de “coleta de casos”.
- Especialistas preferem falar sobre seu domínio através de exemplos completos.
- Quando problemas não são completamente compreendidos ou há muitas exceções às regras.
- Necessidade de construir uma memória que incorpore e transfira experiências.

### Porque utilizar RBC?
- Útil em interpretações abertas e conceitos indefinidos.
- **Vantagens**:
  - Propor soluções rapidamente.
  - Resolver problemas em domínios parcialmente conhecidos.
  - Avaliar soluções que métodos algorítmicos não podem.
  - Relembrar experiências passadas e prevenir problemas.

### Funcionamento do CBR: Ciclo dos 4 RE's
1. **Recuperar**: Busca por casos semelhantes na base de casos.
2. **Reutilizar**: Adaptar a experiência recuperada para propor uma nova solução.
3. **Revisar**: Revisar e ajustar manualmente a solução proposta, se necessário.
4. **Reter**: Armazenar o novo caso aprendido para uso futuro.

### Representação dos casos
- **Formas de Representação**:
  - Vetores de características.
  - Atributo-valor (frames, redes semânticas, objetos, etc.).
  - Lógica de primeira ordem.
- **Desafio**: Equilibrar expressividade e eficiência na representação.

### Similaridade e Recuperação
- **Similaridade**: Função de cálculo de similaridade necessária para recuperar casos semelhantes.
- **Etapas**:
  - **Matching**: Encontrar os N casos mais similares ao caso alvo.
  - **Ranking**: Escolher o melhor caso em relação ao alvo.

### Reutilização
- **Objetivo**: Compensar as diferenças entre o problema-alvo e o caso-fonte.
- **Tipos de Adaptação**:
  - **Estrutural**: Ajuste da solução recuperada.
  - **Derivacional**: Reprocessamento das regras que geraram a solução.

### Revisão
- Avaliar a solução proposta e ajustar, se necessário.
- Mensurar a qualidade da solução.

### Retenção
- **Desafios**:
  - Crescimento incontrolável da base de casos.
  - Degradação da performance do sistema.
  - Incremento no custo de acesso.
- **Soluções**:
  - Seletividade na escolha de novos casos.
  - Remoção ocasional de casos.
  - Expressividade no esquema de indexação.

### Possíveis Problemas
- Aquisição e descrição dos casos podem ser complicadas e demandam conhecimento do domínio.
- Ajuste de pesos dos atributos pode ser difícil.
- Avaliação de soluções nem sempre pode ser imediata.
