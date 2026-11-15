# Quanto tempo leva para quebrar uma senha?

A resposta mais correta possível para essa pergunta é: depende. O tempo para o sucesso de uma operação de quebra depende em muito da velocidade com que conseguimos tentar adivinhar e validar se uma senha é a correta. E isso, por sua vez, depende principalmente da capacidade computacional empregada e da força da senha.

Então, a senha em questão é forte o suficiente, isto é, a maneira como ela foi criada aumenta ou reduz o esforço necessário (o tempo) para adivinha-la? Além disso, qual a capacidade computacional que podemos empregar nesse processo afim de diminuir o tempo total necessário? De modo geral, quebrar uma senha significa gastar tempo testando as possibilidades até encontrar a correta. Então, do ponto de vista da segurança baseada em senhas, quanto mais pudermos dificultar e estender esse tempo, melhor.

Existem diversos fatores que influenciam a criação de senhas fortes e que podem tornar mais fácil ou mais difícil (mais rápido ou mais demorado) quebrar uma senha. Lembre-se de que a intenção é tornar esse processo tão custoso a ponto de inviabilizar a tentativa de ataque. Os três principais fatores que contribuem para isso são:

- Tamanho da senha.
- Grau de aleatoriedade e complexidade da senha.
- Tempo necessário para a operação de transformação da senha.

Abordaremos cada uma delas a seguir.

&nbsp;

## Tamanho das senhas

Para quem busca implementar sistemas seguros ou criar senhas fortes, é correto afirmar que cada caractere adicional conta para aumentar a força da senha. De fato, a recomendação atual do NIST na SP 800–63B-4 é que as senhas criadas pelos usuários tenham, no mínimo, 8 caracteres quando utilizadas em conjunto com mecanismos de MFA, e que, quando utilizadas sozinhas (sem mecanismos adicionais de proteção), deve-se exigir senhas com pelo menos 15 caracteres, o que ajuda a oferecer um nível significativamente maior de segurança.

Além disso, o NIST recomenda que os sistemas permitam senhas de até pelo menos 64 caracteres (NIST SP 800–63B-4, seção 3.1.1.2, “Password Verifier”), para suportar passphrases longas, incentivando os usuários a criar senhas tão longas quanto desejarem e a usar quaisquer caracteres que quiserem (incluindo espaços) para ajudar na memorização (NIST SP 800–63B-4, seção 8.1.2.1, “Passwords”), o que é extremamente útil para proteger também contra outros tipos de ataques off-line, além dos que funcionam testando todas as combinações possíveis.

Isso nos mostra o nível de preocupação das agências de segurança em relação ao tamanho das senhas. De fato, a adição de caracteres é vital, pois cada caractere adicionado pode aumentar significativamente o número de tentativas necessárias para encontrar a senha correta e, consequentemente, o tempo total do processo de quebra. Quanto maior a senha, mais forte e resistente a quebra ela será.

Como um exemplo disso, vamos considerar uma senha de 8 caracteres (a quantidade mínima recomendada pelo NIST), criada a partir das 26 letras minúsculas do alfabeto. O número total de combinações possíveis nesse caso é de 26⁸ = 208.827.064.576 (quase duzentos e nove bilhões de possibilidades). Agora, adicionando mais um caractere (passando para 9), o número de combinações possíveis aumenta para 26⁹ = 5.429.503.679.616 (cerca de 5,4 trilhões de possibilidades), um valor 26 vezes maior.

Como visto, o número de tentativas necessárias aumenta exponencialmente a cada caractere adicionado, o que influencia diretamente o tempo total necessário para encontrar a senha correta.

&nbsp;

## Aleatoriedade e Complexidade das senhas

No caso da complexidade das senhas, aumenta-se a quantidade de símbolos possíveis para preencher cada espaço da sequência de caracteres. O objetivo é tornar a senha ainda mais resistente a operações de quebra, não apenas contra ataques que testam todas as possibilidades de uma sequência específica, como em ataques de força bruta, mas também contra os ataques que utilizam listas de senhas comuns e vazadas, ou sequências previsíveis de caracteres (como vimos anteriormente). Nesse sentido, o objetivo é dificultar o processo de quebra não somente em relação a quantidade de caracteres (o número de tentativas necessárias), mas também em relação a variedade de símbolos que podem ser utilizados em cada posição da sequência (na imprevisibilidade da senha).

Por exemplo, seguindo o mesmo exemplo aplicado na seção anterior, onde consideramos uma senha de 8 caracteres formada apenas por letras minúsculas, imagine agora que, além dessas 26 letras minúsculas, incluamos também as 26 letras maiúsculas do alfabeto como opções de uso. Com maiúsculas e minúsculas, passaríamos a ter 52 caracteres possíveis para preencher cada posição da sequência de 8 caracteres. Nesse caso, a quantidade de tentativas necessárias para encontrar a senha correta saltaria para 53.459.728.531.456 (quase 53,5 trilhões), um valor 256 vezes maior do que as quase 209 bilhões de tentativas necessárias em uma senha de 8 caracteres contendo apenas letras minúsculas.

É necessário lembrar que, nesses cálculos, estamos assumindo o pior cenário possível, onde o agente encontra a senha correta somente na última tentativa, o que representa o número máximo de combinações possíveis e salienta, do ponto de vista de quem deseja garantir a segurança, a importância de criar senhas fortes e dificultar ao máximo um possível processo de recuperação.

&nbsp;

## Tempo necessário para operação de transformação da senha

Aqui, tratamos não exatamente do formato da senha, ou seja, de como a criamos, mas sim das operações computacionais por trás do processo de transformação da senha em texto claro para o seu valor de hash e em sua comparação. Cada tentativa de comparação, isto é, do processo de cálculo do hash e sua comparação com o hash em teste, para verificar se coincidem, leva um tempo maior que zero para ser realizada. Assim, podemos dizer que o tempo geral da operação aumentará quanto maior for o tempo necessário para que cada tentativa aconteça. De fato, essa é a base de KDFs (Key Derivation Functions) lentas como bcrypt, scrypt, Argon2id, PBKDF2.

Levando em conta a quantidade de tentativas necessárias para adivinhação com os números que lidamos nestes exemplos, é certo dizer que o tempo demandado para cada tentativa influenciará fortemente o tempo total do processo de quebra. Ou seja, quanto mais demorada e complexa for a operação computacional de comparação, maior será o tempo demandado para cada tentativa e, consequentemente, maior será o tempo total do processo de quebra.

Isso ocorre pois, embora o hashing seja uma operação utilizada em diversas operações comuns e seja normalmente projetado para ser uma operação rápida, no contexto da segurança de senhas, como mencionado anteriormente, ele deve ser tão lento quanto pudermos suportar. Tornar cada tentativa computacionalmente mais cara pode ajudar muito a tornar uma senha mais resistente a ataques de quebra.

>
Obs: Você deve ter notado que, até agora, a maior parte dos exemplos utilizou cenários baseados em ataques que testam todas as combinações possíveis, como os de força bruta, mesmo que existam outras abordagens de ataques a senha off-line ou mesmo outras abordagens de ataques para recuperar uma senha. Isso foi intencional. A verdade é que ataques desse tipo (brute force) na teoria, são capazes de quebrar qualquer senha, caso haja tempo e recursos suficientes (são especialmente úteis contra senhas de tamanho pequeno, por esse motivo). Mesmo assim, não estou afirmando que essa seja necessariamente a abordagem mais perigosa. Ataques como keylogging, phishing e engenharia social não se tornam menos eficazes quando a senha é longa ou complexa. Esses métodos atingem senhas robustas e senhas simples com a mesma facilidade (NIST SP 800–63B-4 — Apêndice Informativo A — “Strength of Passwords”, seção A.1 “Introduction”). Cada técnica de ataque se mostra mais eficiente em determinados contextos, e a escolha do perpetrador dependerá da situação, obviamente. A intenção é, na verdade, destacar a importância de criar senhas e sistemas suficientemente robustos para tornar a recuperação da senha o mais difícil possível ao agente de um ataque. Dessa forma, independentemente de o agente empregar força bruta, listas de senhas vazadas, dicionários ou qualquer outro método, nosso propósito, do ponto de vista da segurança, é tornar esse processo extremamente custoso e pouco viável.
>

&nbsp;

---

[Índice da pesquisa](../../README.md#%C3%ADndice)
[Índice da pesquisa](../README.md) · [Índice de técnicas](../03-tecnicas-de-quebra/README.md)
