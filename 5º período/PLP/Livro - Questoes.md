## Resolução de Questões - Conceitos de Linguagens de Porgramação, Robert W. Sebesta

### Capítulo 1
1. **Por que é útil para um programador ter alguma experiência no projeto de linguagens, mesmo que ele nunca projete uma linguagem de programação?**
   - Experiência no projeto de linguagens ajuda a entender melhor as limitações e vantagens das linguagens existentes.

2. **Como o conhecimento de linguagens de programação pode beneficiar toda a comunidade da computação?**
   - O conhecimento sobre linguagens permite criar melhores ferramentas e tomar decisões mais informadas sobre quais linguagens usar.

3. **Que linguagem de programação tem dominado a computação científica nos últimos 50 anos?**
   - Fortran.

4. **Que linguagem de programação tem dominado as aplicações de negócios nos últimos 50 anos?**
   - COBOL.

5. **Que linguagem de programação tem dominado a Inteligência Artificial nos últimos 50 anos?**
   - LISP.

6. **Em que linguagem o UNIX é escrito?**
   - C.

7. **Qual é a desvantagem de ter muitas características em uma linguagem?**
   - Pode dificultar o aprendizado e reduzir a legibilidade.

8. **Como a sobrecarga de operador definida pelo usuário pode prejudicar a legibilidade de um programa?**
   - A sobrecarga excessiva pode tornar o código confuso, pois um operador pode ter múltiplos significados.

9. **Cite um exemplo da falta de ortogonalidade no projeto da linguagem C.**
   - Arrays são passados por referência, mas variáveis escalares por valor.

10. **Qual linguagem usou a ortogonalidade como um critério de projeto primário?**
   - ALGOL 68.

11. **Que sentença de controle primitiva é usada para construir sentenças de controle mais complicadas em linguagens que não as têm?**
   - GOTO.

12. **Que construção de uma linguagem de programação fornece abstração de processos?**
   - Subprogramas ou funções.

13. **O que significa para um programa ser confiável?**
   - Um programa confiável cumpre suas especificações em todas as condições.

14. **Por que verificar os tipos dos parâmetros de um subprograma é importante?**
   - Evita erros de tipos e aumenta a segurança do código.

15. **O que são apelidos?**
   - Apelidos são referências múltiplas para a mesma área de memória.

16. **O que é o tratamento de exceções?**
   - É a capacidade de lidar com erros em tempo de execução.

17. **Por que a legibilidade é importante para a facilidade de escrita?**
   - Código legível facilita a escrita e manutenção.

18. **Como o custo de compiladores para uma linguagem está relacionado ao projeto dela?**
   - Linguagens mais complexas tornam os compiladores mais caros de desenvolver.

19. **Qual tem sido a influência mais forte no projeto de linguagens de programação nos últimos 50 anos?**
   - A arquitetura de von Neumann.

20. **Qual é o nome da categoria de linguagens de programação cuja estrutura é ditada pela arquitetura de computadores de von Neumann?**
   - Linguagens imperativas.

21. **Que duas deficiências das linguagens de programação foram descobertas como um resultado da pesquisa em desenvolvimento de software dos anos 1970?**
   - Falta de abstração e controle inadequado sobre processos.

22. **Quais são os três recursos fundamentais de uma linguagem orientada a objetos?**
   - Encapsulamento, herança e polimorfismo.

23. **Qual foi a primeira linguagem a oferecer suporte aos três recursos fundamentais da programação orientada a objetos?**
   - Simula 67.

24. **Dê um exemplo de dois critérios de projeto de linguagens que estão em conflito direto um com o outro.**
   - Simplicidade vs. Potência da linguagem.

25. **Quais são os três métodos gerais de implementar uma linguagem de programação?**
   - Compilação, interpretação pura, implementação híbrida.

26. **Qual produz uma execução de programas mais rápida, um compilador ou um interpretador puro?**
   - Compilador.

27. **Que papel a tabela de símbolos tem em um compilador?**
   - Armazena informações sobre variáveis, funções, etc., usadas durante a compilação.

28. **O que faz um ligador?**
   - Conecta o código do programa com bibliotecas e cria um executável final.

29. **Por que o gargalo de von Neumann é importante?**
   - Limita a velocidade do processamento de instruções e de transferência de dados.

30. **Quais são as vantagens de implementar uma linguagem com um interpretador puro?**
   - Fácil depuração e feedback imediato ao programador.

## Capítulo 3
1. **Defina sintaxe e semântica.**
   - Sintaxe refere-se à forma e estrutura das expressões e sentenças em uma linguagem de programação, enquanto a semântica descreve o significado dessas expressões e sentenças.

2. **Para quem as descrições de linguagens são criadas?**
   - As descrições de linguagens são criadas para avaliadores, implementadores e usuários da linguagem.

3. **Descreva a operação de um gerador de linguagens típico.**
   - Um gerador de linguagens gera sentenças válidas de uma linguagem com base em regras definidas, que podem ser usadas para verificar a sintaxe.

4. **Descreva a operação de um reconhecedor de linguagens típico.**
   - Um reconhecedor de linguagens verifica se uma sequência de símbolos (sentença) está dentro da linguagem, comparando-a com as regras gramaticais da linguagem.

5. **Qual é a diferença entre uma sentença e uma forma sentencial?**
   - Uma sentença é uma cadeia de símbolos terminada que está na linguagem, enquanto uma forma sentencial é qualquer cadeia de símbolos que pode ser parcialmente derivada a partir do símbolo inicial.

6. **Defina uma regra gramática recursiva à esquerda.**
   - Uma regra recursiva à esquerda é aquela em que o símbolo não terminal da esquerda aparece no início do lado direito da regra, como em `A → Aα`.

7. **Que três extensões são comuns para a maioria das EBNFs?**
   - As extensões comuns incluem: agrupamento opcional (`[]`), repetição (`{}`), e escolha alternativa (`|`).

8. **Diferencie a semântica estática da semântica dinâmica.**
   - Semântica estática refere-se às regras que podem ser verificadas em tempo de compilação, como verificação de tipos. A semântica dinâmica refere-se ao comportamento do programa durante sua execução.

9. **Para que servem os predicados em uma gramática de atributos?**
   - Predicados em gramáticas de atributos são usados para impor restrições de semântica estática, como a verificação de compatibilidade de tipos.

10. **Qual a diferença entre um atributo sintetizado e um herdado?**
    - Um atributo sintetizado é calculado a partir dos atributos dos filhos de um nó na árvore de análise, enquanto um atributo herdado é passado de um nó pai para seus filhos.

11. **Como a ordem de avaliação de atributos é determinada para as árvores de uma gramática de atributos?**
    - A ordem é determinada pela dependência entre atributos; atributos herdados devem ser avaliados antes dos sintetizados.

12. **Qual o principal uso das gramáticas de atributos?**
    - Gramáticas de atributos são usadas principalmente para descrever e verificar a semântica estática das linguagens de programação.

13. **Explique os principais usos de uma metodologia e notação para descrever a semântica de linguagens de programação.**
    - São usadas para fornecer uma base formal que permita implementar, testar e verificar o comportamento das linguagens, como através da semântica operacional, denotacional e axiomática.

14. **Por que as linguagens de máquina não podem ser usadas para definir sentenças em semântica operacional?**
    - As linguagens de máquina são muito de baixo nível e complicadas para expressar de forma clara as sentenças e o comportamento de linguagens de programação.

15. **Descreva os dois níveis de uso da semântica operacional.**
    - Semântica operacional natural examina o resultado final da execução de um programa, enquanto a semântica operacional estrutural examina a sequência completa de mudanças de estado durante a execução.

16. **Na semântica denotacional, o que são os domínios sintáticos e semânticos?**
    - O domínio sintático corresponde às estruturas sintáticas da linguagem, enquanto o domínio semântico define os objetos matemáticos que representam o significado dessas estruturas.

17. **O que é armazenado no estado de um programa para semântica denotacional?**
    - O estado de um programa contém os valores de todas as variáveis do programa em um determinado ponto da execução.

18. **Que abordagem semântica é mais conhecida?**
    - A semântica denotacional é a abordagem mais conhecida e rigorosa.

19. **Que duas coisas devem ser definidas para cada entidade de linguagem de forma a construir uma descrição denotacional da linguagem?**
    - Devem ser definidos um objeto matemático e uma função de mapeamento que relaciona essa entidade a esse objeto.

20. **Que parte de uma regra de inferência é o antecedente?**
    - O antecedente é a condição anterior à sentença, que deve ser verdadeira para que a conclusão também seja verdadeira.

21. **O que é uma função de transformação de predicado?**
    - Uma função de transformação de predicado mapeia uma pós-condição para sua pré-condição, garantindo que, se a pós-condição for verdadeira, a pré-condição também será.

22. **O que a corretude parcial significa para um laço?**
    - Corretude parcial significa que o laço é correto para o seu propósito, mas o término não é garantido.

23. **Em que ramo da matemática a semântica axiomática é baseada?**
    - A semântica axiomática é baseada na lógica formal e na teoria da prova.

24. **Em que ramo da matemática a semântica denotacional é baseada?**
    - A semântica denotacional é baseada na teoria das funções matemáticas e recursivas.

25. **Qual é o problema em usar um interpretador puro de software para semântica operacional?**
    - O uso de um interpretador puro de software é muito lento e pode levar a ineficiências, já que cada sentença precisa ser reinterpretada sempre que é executada.

26. **Explique o que as pré-condições e as pós-condições de uma sentença significam na semântica axiomática.**
    - A pré-condição define o estado inicial necessário para a execução de uma sentença, e a pós-condição define o estado resultante esperado após a execução.

27. **Descreva a abordagem de usar semântica axiomática para provar a corretude de um programa.**
    - A semântica axiomática utiliza regras lógicas para verificar se a execução de cada sentença de um programa mantém as pré e pós-condições estabelecidas, provando assim sua corretude.

28. **Descreva o conceito básico de semântica denotacional.**
    - A semântica denotacional mapeia construções sintáticas para objetos matemáticos, fornecendo uma interpretação formal do significado das sentenças de um programa.

29. **De que forma fundamental a semântica operacional e a semântica denotacional se diferem?**
    - A semântica operacional descreve a execução passo a passo de um programa, enquanto a semântica denotacional mapeia o programa diretamente para seu significado matemático, sem considerar a execução passo a passo.

## Capítulo 4
1. **Quais são as três razões pelas quais os analisadores sintáticos são baseados em gramáticas?**

   - Claridade e concisão das descrições de sintaxe
   - As gramáticas podem ser usadas diretamente pelo analisador sintático
   - Modularidade e facilidade de manutenção

2. **Explique as três razões pelas quais a análise léxica é separada da análise sintática.**

   - Simplicidade: a análise léxica é menos complexa
   - Eficiência: otimização seletiva da análise léxica
   - Portabilidade: o analisador léxico pode ser dependente de plataforma

3. **Defina lexema e token.**

   - **Lexema**: Cadeia de caracteres que forma uma unidade lógica, como uma palavra-chave ou identificador.
   - **Token**: Categoria de lexemas, representando o tipo do lexema, como `IDENT` para identificadores.

4. **Quais são as tarefas primárias de um analisador léxico?**

   - Identificar lexemas no código-fonte
   - Gerar tokens para os lexemas identificados
   - Ignorar espaços em branco e comentários
   - Detectar e reportar erros léxicos

5. **Descreva brevemente as três abordagens para a construção de um analisador léxico.**

   - Usar uma linguagem descritiva de expressões regulares para gerar o analisador automaticamente
   - Projetar um diagrama de transição de estados e implementá-lo
   - Construir manualmente uma implementação dirigida por tabela de estados

6. **O que é um diagrama de transição de estados?**

   - Um grafo dirigido em que os nós representam estados e os arcos representam transições entre estados, baseadas em entradas de caracteres.

7. **Por que são usadas classes de caracteres, em vez de caracteres individuais, para as transições de letras e dígitos de um diagrama de estados de um analisador léxico?**

   - Para simplificar o diagrama e reduzir o número de transições, agrupando caracteres similares (como todas as letras ou dígitos) em uma única transição.

8. **Quais são os dois objetivos distintos da análise sintática?**

   - Verificar a correção sintática do programa
   - Produzir uma árvore de análise sintática para uma entrada correta

9. **Descreva as diferenças entre analisadores sintáticos descendentes e ascendentes.**

   - **Descendente**: Começa da raiz e vai em direção às folhas da árvore de análise sintática.
   - **Ascendente**: Começa pelas folhas e constrói a árvore em direção à raiz.

10. **Descreva o problema de análise sintática para um analisador sintático descendente.**

    - Escolher a regra correta de produção para expandir o não terminal mais à esquerda, com base no próximo token da entrada.

11. **Descreva o problema de análise sintática para um analisador sintático ascendente.**

    - Identificar o manipulador, ou seja, a parte da cadeia que deve ser reduzida para seu não terminal correspondente.

12. **Explique por que os compiladores usam algoritmos de análise sintática que funcionam em apenas um subconjunto de todas as gramáticas.**

    - A maioria das gramáticas gerais é muito complexa para ser analisada eficientemente; usar algoritmos para subconjuntos facilita a implementação.

13. **Por que as constantes nomeadas são usadas, em vez de números, para códigos de tokens?**

    - Para melhorar a legibilidade e a manutenibilidade do código, facilitando a compreensão dos tokens.

14. **Descreva como um subprograma de análise sintática descendente recursiva é escrito para uma regra com um único lado direito.**

    - Implementa-se uma função que chama a si mesma para processar os componentes da regra, seguindo a derivação recursiva da gramática.

15. **Explique as duas características das gramáticas que as proíbem de serem usadas como a base para um analisador sintático descendente.**

    - Recursão à esquerda
    - Fatoração inadequada (ambiguidade)

16. **O que é o conjunto FIRST para uma gramática e forma sentencial?**

    - O conjunto de todos os tokens que podem aparecer no início de qualquer sentença derivada de uma forma sentencial específica.

17. **Descreva o teste de disjunção par a par.**

    - Testa se os conjuntos FIRST de cada produção de um não terminal são disjuntos, garantindo que as produções possam ser diferenciadas.

18. **O que é fatoração à esquerda?**

    - Transformar produções recursivas à esquerda em equivalentes não recursivas, para facilitar a análise sintática descendente.

19. **O que é uma frase de uma forma sentencial?**

    - Uma subcadeia de uma forma sentencial que pode ser derivada a partir de um único não terminal.

20. **O que é uma frase simples de uma forma sentencial?**

    - Uma frase derivada a partir de um único passo de produção na gramática.

21. **O que é o manipulador de uma forma sentencial?**

    - A subcadeia mais à direita em uma forma sentencial que pode ser reduzida para um não terminal.

22. **Qual é a máquina matemática em que os analisadores sintáticos descendentes e ascendentes são baseados?**

    - Autômato de Pilha (PDA - Pushdown Automaton)

23. **Descreva três vantagens dos analisadores sintáticos LR.**

    - Podem analisar todas as linguagens de programação
    - Detectam erros sintáticos rapidamente
    - Suportam gramáticas mais complexas que analisadores LL

24. **Qual foi a descoberta de Knuth ao desenvolver a técnica de análise sintática LR?**

    - Que as informações sobre a análise sintática podem ser representadas por um número limitado de estados, armazenados em uma pilha.

25. **Descreva o propósito da tabela ACTION de um analisador sintático LR.**

    - Define as ações (deslocar, reduzir, aceitar ou erro) com base no estado atual e no próximo símbolo de entrada.

26. **Descreva o propósito da tabela GOTO de um analisador sintático LR.**

    - Especifica para qual estado o analisador deve ir após realizar uma redução.

27. **A recursão à esquerda é um problema para analisadores sintáticos LR?**

    - Não, a recursão à esquerda é um problema para analisadores descendentes, mas não afeta os analisadores LR.
