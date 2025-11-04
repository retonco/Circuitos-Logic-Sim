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

Este circuito foi criado utilizando o aplicativo **Digital Logic Sim**, desenvolvido por **Sebastian Lague**, disponível no **itch.io**.
