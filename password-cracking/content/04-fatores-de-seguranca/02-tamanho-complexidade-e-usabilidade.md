# Tamanho, complexidade e tempo necessário para operação de transformação da senha são tudo?

Uma questão extremamente importante é que esses três conceitos, quando aplicados ao contexto real de usuários humanos sendo responsáveis por criar senhas fortes, não contam toda a ópera. A responsabilidade do usuário não acaba no momento da criação da senha. Ele precisará memorizá-la e recuperá-la quando necessário, e a forma humana de pensar inevitavelmente faz com que surjam estratégias que nem sempre estarão alinhadas com as melhores práticas de segurança.

A despeito de já termos discutido as características que tornam uma senha mais forte contra ataques offline, vamos analisar o que as instituições de segurança recomendam sobre como, com base nesse conhecimento, deve-se orientar os usuários sobre como criarem suas senhas:

&nbsp;

O NIST, _(NIST SP 800–63B-4, seção 3.1.1.2, item 5)_ diz:

- _“Verificadores e Provedores de Serviços de Credenciais NÃO devem impor regras adicionais de composição (ex.: exigir mistura de diferentes tipos de caracteres).”_

&nbsp;

O item 1 dessa mesma seção reforça algo que já vimos:

- _“Verificadores e CSPs devem exigir que senhas usadas como mecanismo de autenticação de fator único tenham mínimo de 15 caracteres. Senhas usadas em MFA podem ser menores, mas devem ter no mínimo oito caracteres.”_

&nbsp;

O item 6 diz o seguinte:

- _“Verificadores e CSPs NÃO devem exigir que assinantes troquem suas senhas periodicamente. Entretanto, verificadores devem forçar a troca caso haja evidências de comprometimento.”_

O OWASP segue a mesma linha no _(OWASP Cheat Sheet Serie — Authentication Cheat Sheet — Implement Proper Password Strength Controls)_:

Sobre o tamanho das senhas, assim como já observamos no padrão NIST:

- _“O aplicativo deve impor um tamanho mínimo para as senhas. Se o MFA estiver habilitado, senhas com menos de 8 caracteres são consideradas fracas (NIST SP 800–63B). Se o MFA não estiver habilitado, senhas com menos de 15 caracteres são consideradas fracas (NIST SP 800–63B).”_

Também afirma:

- _“Permitir o uso de todos os caracteres, incluindo Unicode e espaços em branco. Não deve haver regras de composição restringindo o tipo de caracteres permitidos. Não deve haver exigência de letras maiúsculas, minúsculas, números ou caracteres especiais.”_

Também:

- _“Garantir a rotação de credenciais quando houver vazamento de senha, identificação de comprometimento ou mudança na tecnologia do autenticador. Evitar exigir trocas periódicas; em vez disso, incentivar os usuários a escolher senhas fortes e habilitar MFA. De acordo com as diretrizes do NIST, verificadores não devem impor trocas arbitrárias (por exemplo, periódicas).”_

Vemos que, embora a complexidade seja um fator que, ao menos em teoria, aumenta a força das senhas — o que é justamente o nosso objetivo — , há uma tendência entre os órgãos de segurança em, a despeito desse conhecimento, priorizar o tamanho da senha aliado a métodos de autenticação multifator. Mas qual a razão dessa tendência? A própria documentação do NIST nos dá a resposta:

O Apêndice Informativo A — “Strength of Passwords”, seção A.1 “Introduction”, da NIST SP 800–63B-4, diz:

- _“Os seres humanos têm uma capacidade limitada de memorizar segredos complexos e arbitrários, por isso frequentemente escolhem senhas que podem ser facilmente adivinhadas. Para lidar com essas preocupações, serviços online introduziram regras para aumentar a força efetiva dessas senhas. A forma mais notável disso são as regras de composição, que exigem que senhas sejam construídas usando uma mistura de tipos de caracteres (por exemplo, ao menos um dígito, letra maiúscula e símbolo). Porém, análises de bases de senhas vazadas mostram que o benefício dessas regras é menos significativo do que se imaginava, e o impacto na usabilidade e memorização é severo.”_

_“A força efetiva das senhas escolhidas por usuários tem sido frequentemente caracterizada usando o conceito de entropia da teoria da informação. Embora a entropia possa ser calculada facilmente quando há uma distribuição determinística, estimar entropia em senhas criadas por usuários é desafiador. Por isso, uma abordagem mais simples, baseada principalmente no tamanho da senha, tem sido adotada.”_

O documento continua, na seção A.3 — _“Complexity”_, afirmando:

_“Regras de composição são comumente usadas para tentar aumentar a dificuldade de adivinhar senhas escolhidas por usuários. No entanto, pesquisas mostram que os usuários respondem de maneiras bastante previsíveis às exigências impostas por essas regras. Por exemplo, alguém que escolheria ‘password’ como senha provavelmente escolherá ‘Password1’ se for obrigado a incluir uma letra maiúscula e um número, ou ‘Password1!’ se também for exigido um símbolo.”_

_“Senhas altamente complexas introduzem uma nova vulnerabilidade: são menos memoráveis e mais propensas a serem anotadas ou armazenadas de forma insegura. Embora algumas formas de registro não sejam necessariamente vulneráveis, várias delas são. Este é mais um motivo para não exigir senhas excessivamente longas ou complexas.”_

_“Exigências de tamanho e complexidade além das recomendadas aumentam significativamente a frustração do usuário e a dificuldade de uso. Como resultado, muitos usuários acabam contornando essas restrições de maneira contraproducente.”_

Em outras palavras, quando sistemas impõem requisitos de complexidade elevados, os usuários inevitavelmente procuram estratégias para registrar ou memorizar suas senhas, e muitas dessas estratégias acabam subvertendo o propósito original dessas exigências, que é aumentar a segurança das senhas.

Esses comportamentos mostram que, embora os conceitos de tamanho, complexidade e custo computacional sejam os principais fatores relacionados a criação de senhas fortes, eles precisam ser equilibrados com a forma como as pessoas realmente criam, usam e lembram suas senhas. Sem essa consideração, exigências rigorosas podem produzir o efeito contrário ao desejado, incentivando práticas que tornam as senhas menos seguras e mais previsíveis.

---

[Índice da pesquisa](../README.md) · [Índice de técnicas](../03-tecnicas-de-quebra/README.md)
