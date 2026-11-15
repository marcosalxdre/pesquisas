# Ataques de máscara ou conhecimento parcial

Os ataques de máscara são um subconjunto dos ataques de força bruta e funcionam a partir da suposição de que o agente já possui alguma noção sobre o formato de construção da senha, como, por exemplo, o seu tamanho, os tipos de caracteres utilizados ou a posição provável de números, letras e símbolos na sequência. Isso permite aplicar uma força bruta mais direcionada, reduzindo significativamente a quantidade de senhas candidatas e testando apenas as combinações que se encaixam no formato previsto, o que torna o ataque muito mais eficiente.

Imagine, por exemplo, que o responsável por um ataque possua informações a respeito da política de senhas de uma instituição, na qual os usuários são orientados a incluir ao menos uma letra minúscula, um símbolo especial ou que os colaboradores devem seguir um ciclo específico de rotação de senhas. Com essas informações em mãos, torna-se possível criar regras ajustadas a esse padrão, direcionando o ataque e reduzindo exponencialmente o número de senhas candidatas testadas.

Esse “padrão” (máscara), no hashcat, por exemplo, pode ser definido utilizando-se “placeholders”. A ferramenta disponibiliza conjuntos como ?l (todas as minúsculas), ?u (maiúsculas), ?d (dígitos) e ?s (símbolos). O padrão ?u?d?d?d indica uma senha de 4 caracteres começando em letra maiúscula seguida de 3 dígitos.

Um exemplo ajudará a tornar o conceito desta abordagem mais claro:

Considere a senha “Rosa1995” como base:

Imagine que uma abordagem de força bruta pura fosse utilizada para tentar quebrá-la. Nesse cenário, o agente do ataque não possui nenhuma informação prévia sobre a senha e, portanto, tenta quebrá-la “às cegas”.

Dessa forma, ele precisa considerar todos os 95 caracteres imprimíveis do conjunto ASCII — que incluem letras maiúsculas e minúsculas, dígitos e símbolos (excluindo caracteres estendidos, como acentuações) — como possíveis para ocupar cada posição da senha. Uma senha de 8 caracteres formada a partir desse conjunto gera um total de 95^8 combinações, ou seja, 6.634.204.312.890.625 possibilidades (aproximadamente 6,63 quatrilhões de combinações possíveis).

Digamos que o agente possa empregar uma taxa de 100 milhões de tentativas por segundo no processo de quebra, o ataque empregado poderia levar, na pior das hipóteses, 2,1 anos para chegar a senha correta, um período de tempo extremamente longo e difícil de ser sustentado na prática.

Agora, no entanto, o agente tentará resolver o mesmo problema através da abordagem de máscara, e aqui a situação muda drasticamente.

Em vez de tentar tudo, o agente aplicará uma máscara baseada em um conhecimento prévio que obteve sobre como a senha foi construída. Digamos que agora ele possua a informação de que a senha que precisa quebrar possui exatamente os 8 caracteres, e que os últimos 4 caracteres representam um ano de nascimento (portanto, apenas dígitos de 0 a 9).

Embora os quatro caracteres iniciais possam assumir qualquer um dos 95 caracteres do padrão ASCII, o agente aplicará uma máscara que incorpore essas restrições, com o objetivo de reduzir significativamente o número de combinações possíveis e, consequentemente, encurtar o tempo total do ataque.

Com a máscara aplicada, a quantidade total de combinações possíveis é consideravelmente reduzida para 814.506.250.000 (aproximadamente 814,5 bilhões) de combinações, uma quantidade cerca de é 8.145 vezes menor. Mantendo a mesma taxa de 100 milhões de tentativas por segundo do exemplo anterior, o ataque percorreria todo o espaço de busca em cerca de 2 horas e 16 minutos.

Os ataques de máscara representam uma abordagem mais direcionada e eficiente para a quebra de senhas quando comparados à força bruta tradicional. Essa técnica permite a definição de padrões e restrições com base em conhecimentos prévios sobre a estrutura de senhas, o que reduz significativamente o espaço de busca e acelera o processo de cracking. Em muitos cenários, essa otimização é o que torna o ataque viável, enquanto um brute force puro seria insustentável.

---

[Índice da pesquisa](../README.md) · [Índice de técnicas](../03-tecnicas-de-quebra/README.md)
