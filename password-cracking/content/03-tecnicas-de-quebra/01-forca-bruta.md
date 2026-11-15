# Ataques de força bruta

O ataque de força bruta consiste em tentar, de forma sistemática, todas as combinações possíveis de caracteres dentro de uma sequência definida, até que a senha correta seja encontrada.

Os ataques incrementais representam a forma clássica de ataque baseado em força bruta e têm como base três parâmetros simples: tamanho mínimo da senha, tamanho máximo da senha e o conjunto de caracteres que podem aparecer na senha, denominado _“charset”_ ou _“alfabeto”_.

Após a definição desses parâmetros, o ataque começará a gerar todas as combinações possíveis seguindo uma ordem específica, que pode ser alfabética, baseada em um padrão específico de codificação de caracteres ou qualquer outra ordem definida pelo agente ou implementada pela ferramenta.

A forma mais comum consiste em gerar, inicialmente, todas as combinações a partir do tamanho mínimo, avançando progressivamente para as candidatas mais longas. Assim, por exemplo, se utilizássemos um charset composto pelos caracteres minúsculos do alfabeto latino (a-z), configurando o ataque para gerar as combinações em ordem alfabética, com tamanho mínimo de 4 e máximo de 6 caracteres, a geração das candidatas seguiria algo como:

&nbsp;

```
              aaaa                   aaaaa                   aaaaaa
              aaab                   aaaab                   aaaaab
              aaac                   aaaac                   aaaaac
              aaad                   aaaad                   aaaaad
              ....                   ....                    ......
              aaay                   aaaay                   aaaaay
              aaaz                   aaaaz                   aaaaaz
              ....                   ....                    ......
              aaba                   aaaba                   aaaaba
              aabb                   aaabb                   aaaabb
              ....                   ....                    ......
              aazz                   aaazz                   aaaazz
              abaa                   aabaa                   aaabaa
              abab                   aabab                   aaabab
              ....                   ....                    ......
              zzzz                   zzzzz                   zzzzzz
          4 caracteres           5 caracteres            6 caracteres
```

&nbsp;

Como visto, a cada tentativa, o valor do caractere na última posição é incrementado. Quando todas as possibilidades de “a” até “z” são esgotadas, o caractere na penúltima posição é incrementado e o processo é reiniciado, repetindo esse ciclo sucessivamente.

A geração começa pelo comprimento mínimo (4). As combinações, neste caso, são testadas em ordem alfabética, desde aaaa até a última combinação de 4 caracteres (zzzz). Após esgotar todas as combinações possíveis de 4 caracteres, o ataque passa para o próximo comprimento (5). Novamente, as senhas são testadas em ordem alfabética, desde aaaaa até zzzzz. Em seguida, o ataque avança para o comprimento máximo especificado (6). A progressão continua alfabeticamente, de aaaaaa até zzzzzz, isto é, até que todo o espaço de combinações possíveis seja completamente percorrido.

Essa é a maneira mais comum de executar um ataque incremental, mas não é a única forma possível, como mencionado anteriormente. O processo de geração pode seguir uma lógica de incrementação totalmente diferente.

O espaço total de busca (keyspace) de um ataque incremental pode ser calculado elevando o tamanho do charset ao comprimento mínimo da senha e, em seguida, a cada comprimento intermediário, até o comprimento máximo, somando todos esses valores.

Utilizando como base nosso exemplo anterior onde temos um charset de tamanho 26 (a–z), um tamanho mínimo de 4 e um tamanho máximo de 6:

&nbsp;

```
    k = 26⁴ + 26⁵ + 26⁶
    26⁴ = 456.976
    26⁵ = 11.881.376
    26⁶ = 308.915.776
    k = 456.976 + 11.881.376 + 308.915.776
    k = 321.254.128
```

&nbsp;

temos, nesse caso, cerca de 321 milhões de combinações possíveis.

A técnica de força bruta costuma ser altamente eficaz contra senhas curtas (menores que 7–8 caracteres) armazenadas com algoritmos de hashing inadequados para este fim. Computadores com hardware relativamente comum conseguem quebrar senhas nesse formato em poucos segundos ou até instantaneamente.

Por outro lado, o uso de senhas longas, combinado com algoritmos apropriados pode rapidamente tornar essa técnica inviável do ponto de vista prático. Alguns exemplos de algoritmos adequados para o armazenamento de senhas, como visto anteriormente, são: scrypt, bcrypt, Argon2id e PBKDF2.

Embora, na teoria, seja verdade que qualquer senha possa ser quebrada por esse método, na prática isso dependerá inteiramente de suas características, como tamanho, complexidade e o algoritmo de hashing utilizado. O aumento exponencial no número de permutações pode superar em muito o tempo e/ou o poder computacional disponíveis. Quando o custo computacional necessário ultrapassa aquilo que o agente do ataque consegue sustentar, seja em tempo, poder de processamento ou outros recursos, a técnica simplesmente pode deixar de ser viável.

&nbsp;

---

[Índice da pesquisa](../../README.md#%C3%ADndice)
