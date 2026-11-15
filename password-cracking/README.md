# Password Cracking: Conceitos Básicos e Principais Técnicas Utilizadas

**Autor:** Marcos Pinheiro   
**Origem:** Artigo originalmente publicado no Medium no perfil: https://medium.com/@marcos.aba

&nbsp;

<div align="center">
  <img src="mídias/passwordcracking.png" alt="Password Cracking" title="Password Cracking" width="400">
</div>

## Introdução

As senhas são um dos mecanismos de segurança mais antigos e ainda hoje constituem a forma mais comum de autenticação digital. Elas funcionam como “chaves de acesso” e nos ajudam a proteger dispositivos, sistemas e informações sensíveis.

Assim como toda forma de proteção criada com o objetivo de resguardar algo de valor, o uso de senhas como mecanismo de segurança, igualmente, sempre envolveu a existência de vulnerabilidades e motivou tanto o desenvolvimento de técnicas para contornar seu uso quanto o estudo dessas fraquezas, visando aprimorar sua eficácia.

Especificamente no caso das senhas como forma de proteger sistemas e dispositivos digitais, a quebra de senhas, o assunto principal deste artigo, surgiu justamente como uma maneira de contornar tal mecanismo.

Este pequeno artigo tem o objetivo de esclarecer de forma básica a abordagem de quebra de senhas off-line (Password Cracking) e os conceitos relacionados. A quebra de senhas off-line ocorre quando o perpetrador do ataque já possui os hashes de senha e o processo de recuperação do texto em claro é realizado de maneira offline.

Há uma outra abordagem de ataque a senhas conhecida como “Password Guessing”, em que tentativas de adivinhação da senha (ou credenciais) são realizadas contra e interagindo com serviços on-line através das suas interfaces de autenticação. Esta abordagem não será tratada a fundo neste material, sendo mencionada brevemente apenas para explicar a diferença entre ataques on-line e off-line; a aquisição dos hashes de senha, por sua vez, também está fora do escopo deste artigo.

> Obs: Visto que o ataque de quebra de senhas pode ter razões legítimas, o termo “agente” é usado neste artigo para se referir aquele que executa a operação de quebra, independente de sua motivação.

&nbsp;

## Índice

Os tópicos estão organizados por assunto. Clique em qualquer título para abrir diretamente o respectivo arquivo.

### 1. Fundamentos

1. [O que são senhas?](content/01-fundamentos/01-o-que-sao-senhas.md)
2. [Como as senhas são armazenadas?](content/01-fundamentos/02-armazenamento-de-senhas.md)

### 2. Password Cracking

1. [Conceito e casos de uso](content/02-password-cracking/01-conceito-e-casos-de-uso.md)
2. [Diferenças entre ataques online e offline](content/02-password-cracking/02-ataques-online-e-offline.md)

### 3. Técnicas de quebra

1. [Visão geral das técnicas](content/tecnicas-de-quebra)
2. [Ataques de força bruta](content/03-tecnicas-de-quebra/01-forca-bruta.md)
3. [Ataques de dicionário](content/03-tecnicas-de-quebra/02-ataques-de-dicionario.md)
4. [Ataques combinados](content/03-tecnicas-de-quebra/03-ataques-combinados.md)
5. [Ataques híbridos](content/03-tecnicas-de-quebra/04-ataques-hibridos.md)
6. [Ataques de máscara ou conhecimento parcial](content/03-tecnicas-de-quebra/05-ataques-de-mascara.md)

### 4. Fatores de segurança

1. [Quanto tempo leva para quebrar uma senha?](content/04-fatores-de-seguranca/01-tempo-de-quebra.md)
2. [Tamanho, complexidade e usabilidade](content/04-fatores-de-seguranca/02-tamanho-complexidade-e-usabilidade.md)

### 5. Ferramentas

1. [Hashcat e John the Ripper](content/05-ferramentas/hashcat-e-john-the-ripper.md)

### 6. Encerramento e referências

1. [Conclusão e informações do autor](content/06-conclusao/conclusao.md)
2. [Referências bibliográficas](content/referencias.md)

---

[Voltar ao índice geral de pesquisas](../README.md)
