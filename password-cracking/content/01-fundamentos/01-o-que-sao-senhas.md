# O que são senhas?

&nbsp;

Primeiramente, é importante definir o que é uma “senha”. Em termos gerais, podemos definir uma senha como sendo um código secreto, que geralmente existe na forma de uma palavra, frase ou como uma sequência aleatória de caracteres. Uma “senha” é combinada entre as partes envolvidas num processo de reconhecimento, sendo utilizada para confirmar a identidade e/ou autorizar acesso a algum local e/ou recurso. Em sistemas digitais, mais especificamente, as senhas (também conhecidas como passwords), são normalmente representadas por palavras ou alguma sequência arbitrária de caracteres, que podem incluir letras, números e outros símbolos. Se os caracteres permitidos forem restritos a números, o segredo é geralmente chamado de número de identificação pessoal (PIN).

Segundo as Diretrizes de Identidade Digital do NIST (SP 800–63 e 800–63B-4 [Versão Atualizada 2025] Digital Identity Guidelines): “Uma senha é um tipo de autenticador de segredo memorizado (memorized secret authenticator), comumente referido como uma senha (password) ou, se numérica, um PIN, sendo um valor secreto destinado a ser escolhido e memorizado pelo usuário” (NIST SP 800–63B-4, Seção 3.1.1, subseção 3.1 “Password”).

No glossário do NIST, esse conceito é definido como “um tipo de autenticador composto por uma cadeia de caracteres que deve ser memorizada ou ser memorável para o assinante, permitindo que o requerente demonstre algo que ele sabe como parte de um processo de autenticação” (NIST SP 800–63–4, Seção B. Glossary, [Password]).

Utilizando a terminologia das Diretrizes de Identidade Digital do NIST, o segredo é mantido por uma parte chamada requerente (claimant), enquanto a parte que verifica a identidade do requerente é chamada de verificador (verifier). Quando o requerente demonstra com sucesso o conhecimento da senha ao verificador através de um protocolo de autenticação estabelecido, o verificador consegue inferir a identidade do requerente com base em dados armazenados (NIST SP 800–63–3, seção 4.3.3).

&nbsp;

<div align="center">
  <img src="../../mídias/password.png" alt="Password" title="Password" width="500">
</div>

&nbsp;

Como complemento, pode-se destacar que senhas são geralmente utilizadas junto a um nome de usuário ou outro meio de identificação. Essa combinação (senha + nome de usuário) é conhecida como “credenciais”.

Os nomes de usuário representam a parte fixa das credenciais e, por consistirem geralmente de alguma variação do nome real do usuário ou como um endereço de e-mail, informações que costumam ser públicas e que, além disso, costumam ser convenientemente reutilizadas entre diferentes serviços, acabam se tornando bastante previsíveis.

Da perspectiva de um ataque a senhas, quando o agente obtém o nome de usuário de um recurso que utiliza apenas esse mecanismo como forma de proteção, já possui metade das informações necessárias para acessá-lo, restando “somente” obter a senha.

---

[Índice da pesquisa](../../README.md#%C3%ADndice) 
