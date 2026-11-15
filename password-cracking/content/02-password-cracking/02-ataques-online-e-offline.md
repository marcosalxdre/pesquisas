# Diferenças entre ataques a senhas online e offline

Como mencionado no inicio deste artigo, existem duas formas pelas quais ataques a senhas podem ocorrer: Ataques online e offline. Antes de abordarmos as técnicas de quebra de senhas offline, explicaremos brevemente as diferenças entre essas duas abordagens.

&nbsp;

## _**Ataques Online**_

Como vimos brevemente na introdução deste artigo, os ataques online ocorrem com o agente tentando adivinhar senhas interagindo diretamente com a interface de login de um site ou serviço online. É o tipo tradicional de ataque que você esperaria contra um terminal SSH exposto, uma aplicação web ou qualquer outra interface de autenticação.

Nesses ataques, o agente, por meio de alguma ferramenta automatizada ou script especializado, realiza um grande número de tentativas testando combinações de usuário e senha contra um portal de autenticação, na esperança de que alguma tentativa seja a correta.

Existem algumas limitações quando falamos de ataques a senhas online. Por exemplo, questões como a latência da rede, tempo de resposta do sistema atacado (lembre-se que a interação acontece em tempo real) e mecanismos de segurança que podem limitar a quantidade de tentativas de autenticação após um número de tentativas falhas, dificultam ou retardam ataques on-line.

Outra limitação é que os ataques online são extremamente ruidosos, ou seja, fazem muito “barulho” e acabam gerando bastante tráfego suspeito na rede e, por isso, é muito provável que sejam detectados por praticamente qualquer mecanismo de detecção e alerta. Há técnicas utilizadas para contornar essas limitações, contudo, como mencionado anteriormente, uma explicação detalhada a respeito dessa abordagem não está no escopo deste artigo.

&nbsp;

## Ataques Offline

Os ataques off-line, por sua vez, ocorrem quando o agente, por determinado motivo, obtém acesso a hashes de senha e pode realizar a quebra localmente em seu sistema. Dessa forma, não há interação direta com aplicações ou serviços ativos.

Hashes, como você já sabe, são uma representação ilegível da senha gerada a partir de funções de hashing. Quando um sistema salva sua senha, ele não a armazena (ou pelo menos não deveria ) em texto claro. Em vez disso, ele gera o hash (digest) da senha e armazena esse valor. Se sua senha for qwerty, por exemplo, seu sistema armazena algo como d8578edf8458ce06fbc5bb76a58c5ca4. Dessa forma, se alguém obtivesse acesso a esse dado, não seria capaz de visualizá-lo em texto claro diretamente.

Quando o usuário faz login num computador, o sistema pega a senha que o usuário digitou, calcula o hash correspondente e compara com o hash armazenado no momento em que o usuário definiu a senha. Se os hashes coincidirem, o acesso é concedido. Um ataque a senhas offline utiliza esse hash e tenta descobrir o valor em texto claro a partir dele.

Os motivos que levam alguém a obter acesso ao(s) hash(es) de senhas podem variar, desde um administrador tentando recuperar uma senha esquecida por um usuário, até criminosos que obtêm acesso a esses dados de forma ilegal comprometendo sistemas. Os casos de uso podem variar, mas a questão principal é que, nesse cenário, tendo o hash da senha em mãos e armazenado localmente, a operação de quebra não encontrará nenhuma limitação, exceto a capacidade computacional disponível para ser utilizada e a força dos algoritmos de hashing, que podem dificultar significativamente a recuperação da senha original.

Em termos de vantagens, a diferença entre ataques de senha offline e online é significativa. Em um ataque offline, por não interagir diretamente com serviços ativos, o ataque permanece fora do alcance dos sistemas de detecção, tornando-se praticamente invisível para a equipe de segurança. Proteções comuns como bloqueios temporários ou permanentes de contas e IPs, ou CAPTCHAs, não têm efeito. No caso do ataque à senha de uma conta, por exemplo, após realizar a quebra em seu próprio ambiente e descobrir a senha em texto claro, o agente realizaria apenas uma tentativa correta na aplicação.

A velocidade que pode ser empregada no ataque é outra grande diferença. Enquanto ataques online são limitados pela latência da rede, pelo tempo de resposta da aplicação e por restrições de taxa, os ataques offline permitem o uso de recursos de alto desempenho, como GPUs potentes, redes de computação distribuída e hardwares especializados, para testar milhões ou até bilhões de combinações de senhas em alta velocidade, sem gerar alertas. Nesse caso, a única limitação para o agente é a capacidade computacional disponível, mais a força do algoritmo de hashing utilizado.

&nbsp;

---

[Índice da pesquisa](../../README.md#%C3%ADndice)
