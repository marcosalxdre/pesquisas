# Ataques com Base em Dicionário

Os ataques baseados em dicionário, também conhecidos como ataques por wordlists, utilizam um arquivo de texto pré-compilado contendo palavras, frases e diversas variações comumente empregadas como senhas (por exemplo: “qwerty”, “admin123!”, “p@ssw0rd”).

Esse tipo de ataque testa sistematicamente cada item da lista. Ou seja, cada candidata a senha presente no arquivo é lida sucessivamente, tem seu hash calculado e, em seguida, é comparada com o(s) hash(es) de entrada, a fim de verificar se alguma corresponde à senha correta. Essencialmente, gerar tentativas de senha significa apenas ler um arquivo de texto linha por linha. O ataque testará cada palavra sucessivamente, até encontrar a senha correta ou até que todo o dicionário tenha sido completamente percorrido.

Algumas ferramentas permitem a utilização de mais de um dicionário. Nesses casos, os dicionários costumam ser processados um por um, de forma sequencial. O sistema avança automaticamente para o próximo arquivo somente após todas as senhas do dicionário atual terem sido testadas.

O espaço de busca (keyspace) é representado pelo número total de senhas contidas no dicionário, ou, caso o ataque utilize mais de um deles, pela soma da quantidade de senhas de cada dicionário.

Os ataques baseados em dicionário partem do pressuposto de que os usuários tendem a reutilizar senhas comuns e, por isso, foca nas palavras mais prováveis, em vez de tentar todas as combinações possíveis. Isso torna o processo significativamente mais eficiente em termos de tempo e de recursos computacionais quando comparado às abordagens exaustivas.

Esses “dicionários” podem chegar a conter milhões de senhas, formadas a partir de diversos vazamentos de dados ocorridos ao longo dos anos ou criadas com base em contextos específicos, como um determinado idioma ou cenário particular. Um dos dicionários mais conhecidos e amplamente utilizados é o rockyou.txt, que contém cerca de 14,34 milhões de senhas. Esse conjunto de dados surgiu no final de 2009, após o vazamento de mais de quase 33 milhões de credenciais de usuários, comprometidas durante um ataque à empresa RockYou.

Dedicar tempo à criação de um “dicionário” personalizado, a partir de pesquisas sobre um alvo específico, pode aumentar consideravelmente as chances de sucesso em um ataque. Em contrapartida, essa estratégia tende a restringir o escopo de uso da lista, tornando-a menos aplicável a outros cenários.

Os ataques de dicionário são especialmente relevantes em cenários onde a escolha de senhas fracas, previsíveis ou reutilizadas é comum. Muitas credenciais são construídas a partir de palavras do cotidiano, nomes próprios, datas, sequências simples ou pequenas variações desses elementos, o que pode reduzir de forma significativa o esforço necessário em operações de quebra de senhas.

&nbsp;

---

[Índice da pesquisa](../../README.md#%C3%ADndice)
