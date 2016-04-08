# IF688 Compiladores - Primeira Entrega
Para poder executar os testes automáticos da sua submissão, ao fim de sua especificação léxica, após definir todos os elementos da linguagem, inclua a seguinte linha:
. { throw new RuntimeException("Caractere ilegal! '" + yytext() + "' na linha: " + yyline + ", coluna: " + yycolumn); }

Desta forma, caso o programa contenha algum caractere não reconhecido pela especificação léxica, o analisador deve lançar uma exceção indicando este problema. 

Este exercício tem o objetivo de exercitar os conceitos de análise léxica vistos em sala de aula. A ideia é implementar um analisador léxico para a linguagem MiniJava, que consiste em um subconjunto de Java, cujos elementos léxicos são descritos abaixo. 

Instruções para submissão da resposta: Utilize o gerador de analisadores léxicos JFlex para implementar o analisador. Estamos montando um sistema de submissão para a disciplina, mas por enquanto enviem o arquivo via Google Classroom mesmo. O único arquivo que deve ser submetido é o arquivo fonte .jflex, e o nome do arquivo deve ser o seu login. Então, no meu caso seria lmt.jflex. Alguns programas válidos em MiniJava estão em anexo nesta postagem, para que vocês testem o analisador antes da submissão. 

Como sugestão, também indico você usar algum sistema de controle de versão online, como GitHub ou BitBucket, para ir desenvolvendo o analisador. Caso utilize, também inclua o link para o repositório com a sua resposta, além do arquivo submetido. 


### Elementos Léxicos de MiniJava

- Whitespace: espaços em branco, quebra de linha, tabulação e carriage return ( \n \t \r \f);

- Comentários: os dois tipos de comentário são possíveis, comentários de linha, iniciando com // e indo até o final da linha, e comentários de múltiplas linhas, que consistem de qualquer texto entre /* e */, sem considerar aninhamento;

- Palavras reservadas: boolean, class, public, extends, static, void, main, String, int, while, if, else, return, length, true, false, this, new, System.out.println; 
(Por simplicidade e para facilitar a implementação do compilador, MiniJava trata System.out.println como uma palavra reservada, não como uma chamada do método println.)

- Operadores: &&, <, ==, !=, +, -, *, !; 
(não há operador de divisão, por enquanto)

- Delimitadores e pontuação: ; . , = ( ) { } [ ]

- Identificadores: um identificador começa com uma letra ou underline e é seguido por qualquer quantidade de letras, underline e dígitos. Apenas letras entre A/a e Z/z são permitidos, há diferença entre maiúscula e minúscula. Palavras-chave não são identificadores;

- Literais Inteiros: uma sequência de dígitos iniciada com qualquer um dos dígitos entre 1 e 9 e seguida por qualquer número de dígitos entre 0 e 9. O dígito 0 também é um inteiro. 

Comentários e whitespace não tem significado algum, exceto para separar os tokens.
