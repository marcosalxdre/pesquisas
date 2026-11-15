# Visão geral das técnicas

 Nesta parte do material serão abordadas as principais técnicas utilizadas em operações de quebra de senhas off-line. Será  possível visualizar, por exemplo, como cada técnica gera candidatas a senha, quais suposições cada uma delas adota sobre o espaço de senhas (keyspace) e em quais cenários o uso dessas técnicas tende a ser mais ou menos eficaz.

É importante observar que o conceito teórico dessas técnicas pode apresentar variações dependendo da ferramenta utilizada. Além disso, por não possuírem uma nomenclatura universalmente padronizada, uma mesma técnica pode receber nomes distintos em diferentes ferramentas, com algumas dessas abordagens até sobrepondo-se às outras em termos de funcionamento. Veremos isso de forma mais clara quando tratarmos das ferramentas utilizadas nas operações de quebra.

De modo geral, contudo, as técnicas podem ser agrupadas em duas abordagens principais que constituem a base da maioria das ferramentas de quebra de senhas: ataques de dicionário (lista de palavras) e força bruta (busca exaustiva). A partir dessas duas abordagens, surgem variações, como ataques híbridos, combinados e baseados em máscaras, entre outros.

Há também uma outra abordagem conhecida como abordagem probabilística, que inclui métodos como PCFG, Markov e alguns modelos derivados. Essa abordagem é bastante conhecida e funciona utilizando estatística para testar os palpites mais prováveis antes dos demais, tornando a operação de quebra mais eficiente. Por ser uma abordagem um pouco mais avançada, tanto no conceito quanto na implementação, não a discutirei neste texto. No entanto, se desejar, você pode encontrar mais a respeito aqui.

&nbsp;

--- 

[Índice da pesquisa](../../README.md#%C3%ADndice) - [índice de técnicas de quebra](content/03-tecnicas-de-quebra)
