
# Circuitos-Logic-Sim

## 4-bit Adder

### Entradas
- **IN (A)**: É o primeiro número binário, com 4 bits (A0, A1, A2, A3).  
- **IN (B)**: É o segundo número binário, também com 4 bits (B0, B1, B2, B3).  

Essas duas entradas são representadas pelos blocos **4–1BIT**, que farão a operação de soma bit a bit.

### Saídas
- **OUT (SOMA – 4 bits)**: Mostra o resultado final da soma binária dos dois números (S0, S1, S2, S3).  
- **OUT (CARRY OUT)**: Também chamado de **bit de transporte**, é o “vai-um” que sobra da última soma, indicando que o resultado passou do limite de 4 bits.

### Explicação
O **4-bit Adder** (somador de 4 bits) é um circuito combinacional que soma **dois números binários de 4 bits**, gerando um **resultado de 4 bits** e, às vezes, um **bit de transporte (carry out)** quando a soma ultrapassa o valor máximo que 4 bits conseguem representar.

O circuito é formado por:
- **1 Half Adder (somador de meio bit)** → usado para o primeiro bit (bit menos significativo).  
- **3 Full Adders (somadores completos)** → usados para os outros três bits.

#### Half Adder
O *half adder* (somador de meio bit) é o circuito mais simples usado para realizar a soma de dois bits binários.  
Não possui entrada de transporte (carry in) e por isso é chamado de “meio somador”.  

É montado com:
- Uma **porta XOR** para calcular a soma 
- Uma **porta AND** para gerar o carry 

Como não possui entrada de carry, geralmente é usado como a primeira etapa na construção de somadores maiores.

#### Full Adder
Cada *full adder* soma três valores:
1. Um bit de A  
2. Um bit de B  
3. O carry (bit de transporte) que veio da soma anterior  

O *carry out* de um somador vai para o *carry in* do próximo, formando uma cadeia de somas, até chegar no último bit.

---

### O que é o Ripple Carry Adder
O tipo de somador usado aqui é chamado de **Ripple Carry Adder**.  
Isso quer dizer que o **bit de transporte (carry)** vai sendo "carregado" de um somador para o outro até chegar ao final.

Em outras palavras:
- O primeiro somador faz a soma dos bits iniciais.  
- Se sobrar um “vai-um” (carry), ele é passado para o próximo somador.  
- Esse processo se repete até o último bit.

Assim, o circuito consegue somar dois números binários, bit por bit, de forma sequencial.

---

## Full Subtractor

### Entradas
- **A**: Bit minuendo, ou seja, o valor principal do qual será feita a subtração.
- **B**: Bit subtraendo, ou seja, o valor que será subtraído.
- **Borrow In**: Indica se houve empréstimo da subtração anterior (bit menos significativo).

### Saídas
- **Diff (Diferença)**: Resultado final da subtração entre **A**, **B** e **Borrow In**.
- **Borrow Out**: Indica se será necessário “emprestar” do bit à esquerda.

### Estrutura do Circuito

O *full subtractor* (subtrator completo) é formado por **duas partes menores** chamadas *half subtractors* (meios subtratores) e **uma porta OR** no final.

Para isso, o circuito recebe **três valores de entrada (A, B e Borrow In)** e realiza uma subtração entre eles, **bit por bit**.

Resultando em:
- **Diff:** resultado final da subtração  
- **Borrow Out:** indica se foi necessário pegar “1” do próximo bit mais à esquerda

#### Primeiro Half Subtractor:
- **Entradas:** A e B  
- **Função:** faz uma subtração simples entre esses dois bits.  
- **Saídas:**
  - `diff₁`: resultado da primeira subtração 
  - `borrow₁`: indica se foi preciso “pegar emprestado” 

#### Segundo Half Subtractor:
- **Entradas:** `diff₁` (diferença anterior) e `Borrow In` (empréstimo da subtração anterior)  
- **Função:** faz nova subtração levando em conta o empréstimo.  
- **Saídas:**
  - `diff`: diferença final  
  - `borrow₂`: indica novo empréstimo 

#### Combinação dos Empréstimos:
As duas saídas de empréstimo (`borrow₁` e `borrow₂`) são unidas com **uma porta OR**, resultado no `Borrow Out`

Isso mostra se o circuito precisou “pegar emprestado” no total, independente da etapa.

---

Todos os circuitos foram criados utilizando o aplicativo **Digital Logic Sim**, desenvolvido por **Sebastian Lague**, disponível no **itch.io**.
