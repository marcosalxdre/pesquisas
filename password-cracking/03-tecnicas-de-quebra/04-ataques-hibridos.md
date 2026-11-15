# Ataques Hibrídos

Ataques híbridos combinam algumas características dos ataques de dicionário e dos ataques de força bruta. Nessa abordagem, uma lista de palavras é utilizada como base, exatamente como ocorre nos ataques de dicionário, enquanto uma máscara definida acrescenta combinações de caracteres por meio de força bruta dentro de um espaço de caracteres determinado.

Na prática, isso significa pegar cada palavra do dicionário e anexar variações inteligentes geradas pela máscara, como a inclusão de números, letras ou outras sequências de caracteres, compondo novas candidatas para testar.

O Hashcat descreve em seu site duas abordagens distintas para a técnica de ataque híbrido que servem como um bom exemplo: Hybrid wordlist + mask e Hybrid mask + wordlist.

Basicamente, o ataque se comporta das seguintes formas, dependendo da abordagem escolhida:

### **Hybrid wordlist + mask:**

Uma única palavra do dicionário é concatenada com todas as strings possíveis geradas pela máscara. O número de senhas efetivamente testadas corresponde ao keyspace da máscara.

Nesse caso, se tivéssemos um dicionário contendo a palavra “cafe” e utilizássemos como base uma máscara que gera todas as combinações possíveis de dois dígitos até um limite especificado — por exemplo, até 35 — as candidatas formadas a partir dessa abordagem seriam:

cafe00
cafe01
cafe02
…
cafe34
cafe35

### **Hybrid mask + wordlist:**

Uma única string gerada pela máscara é concatenada com todas as palavras do dicionário.

Assim, se tivéssemos um dicionário com as palavras “sol”, “lua”, “vento”, “terra” e “estrela”, e utilizássemos como base uma máscara que gera a string “ab#”, essa única string seria concatenada com todas as palavras do dicionário, o que produziria novas candidatas como:

ab#sol
ab#lua
ab#vento
ab#terra
ab#estrela

É muito comum, em diversos ambientes corporativos, que usuários, seja para adequar suas senhas às políticas da instituição ou simplesmente por hábito, criem credenciais a partir de uma palavra comum do dicionário e adicionem um número, um ano ou alguma sequência previsível no início ou no fim de suas senhas. Nesses cenários, o método de ataque híbrido se mostra particularmente eficaz, pois explora exatamente essa lógica de construção das senhas, combinando uma palavra-base com todas as variações geradas automaticamente a partir de uma máscara previamente definida.

---

[Índice da pesquisa](../README.md) · [Índice de técnicas](../03-tecnicas-de-quebra/README.md)
