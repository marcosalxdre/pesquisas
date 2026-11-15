# Ataques Combinados

Os ataques combinados seguem quase a mesma lógica do ataque de dicionário clássico, exceto pelo fato de que, ao invés de utilizar apenas um dicionário por vez e testar apenas uma palavra isoladamente, esse ataque funciona formando combinações de palavras ou frases montadas a partir de dicionários distintos.

Nesse caso, ao especificar dois dicionários como entrada, geralmente denominados dicionários da esquerda e da direita, as strings pertencentes ao dicionário da esquerda são estendidas por meio da concatenação com as strings do dicionário da direita, formando as novas candidatas que serão testadas.

Um exemplo pode ser útil para entendermos melhor o conceito desse ataque.

Imagine que um dos dicionários, o dicionário da esquerda, contenha as palavras “amor” e “pipa”. Já o segundo, o dicionário da direita, possua as palavras “gato” e “bola”. Dessa forma, um ataque combinado geraria uma lista de novas candidatas a senha formadas pela concatenação das strings de ambos os dicionários, resultando em novas candidatas como:

&nbsp;

**amorgato**   
**amorbola**  
**pipagato**   
**pipabola**

&nbsp;

Em ataques combinados, o número total de combinações possíveis (keyspace) é obtido multiplicando-se o total de entradas de cada dicionário utilizado no ataque. De forma geral, o keyspace pode ser representado como k = d1 × d2 × … x dn. Assim, se tivéssemos dois dicionários modestos com 10.000 palavras cada, um ataque combinado teria um keyspace de 100 milhões de variações de senhas ou passphrases a serem testadas.

É possível aplicar regras de mutação para modificar as palavras dos dicionários, como variações de capitalização, substituições de caracteres e outras transformações comuns e também utilizar mais de dois dicionários, mas essa é uma questão de implementação do ataque e pode ou não estar disponível dependendo da ferramenta utilizada.

O comportamento implementado por essa técnica de ataque se torna especialmente relevante à medida que recomendações de instituições de segurança, como o NIST, passam a enfatizar o tamanho da senha como o principal fator relacionado ao aumento da sua robustez. Essa recomendação pode ser colocada em prática por administradores de sistemas e usuários por meio da criação de senhas compostas por duas ou mais palavras.

O ataque combinado surge, então, como uma técnica especialmente relevante para o comprometimento de senhas longas, pois permite testar combinações extensas evitando o elevado custo computacional e de tempo característico do brute force e também superar a limitação de alcance dos ataques de dicionário clássico.

&nbsp;

---

[Índice da pesquisa](../../README.md#%C3%ADndice)
