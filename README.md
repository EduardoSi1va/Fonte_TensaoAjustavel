# Fonte de Tensão Ajustável
Projeto desenvolvido para a disciplina [SSC0180 - Eletrônica para Computação], ministrada pelo Professor Eduardo do Valle Simôes.

# Integrantes do Grupo 13:
| Aluno | Nº USP |
|---|---|
| André Campanholo Paschoalini | 14558061 |
| Eduardo Poltroniere da Silva | 16862892 |
| Felipe Fabiano das Chagas | 16811922 |
| Pedro Hamamoto da Palma | 16818280 |

# Explicação do Projeto
O circuito deve ser capaz de transformar uma tensão alternada de 127V em contínua, para o intervalo de 3V a 12V e entregar uma corrente de saída de 100mA, em que a regulagem de tensão deve ser feita através de um potenciômetro.

# Lista dos Componentes
Cabem aqui apenas os componentes adquiridos para a execução do trabalho, excetuando componentes emprestados ou que já eram de posse de algum integrante do grupo.
| Componente | Especificação | Quantidade | Preço |
|---|---|---|---|
| Potenciômetro | 1W B5K B-16 | 1 | R$ 7,00 |
| Capacitor | 470μF, 35V | 2 | R$ 5,60 |
| Transistor 2N3904 | 60V, 0.2A, 0.65W | 2 | R$ 3,20 |
| Resistor CR25 100 | 100Ω | 10 | R$ 0,70 |
| Resistor CR25 820 | 820Ω | 10 | R$ 0,70 |
| Resistor CR25 1K | 1000Ω | 10 | R$ 0,70 |
| Resistor CR25 1.8K | 1800Ω | 10 | R$ 0,70 |
| Diodo | 1N4007 | 10 | R$ 2,00 |
| Diodo Zener | 1N4743 13V, 1W | 2 | R$ 1,00 |
| LED Vermelho | 5mm | 2 | R$ 1,00 |
| Jumper | Macho x Macho 20cm | 10 | R$ 7,00 |
| Total |   |   | R$ 29,04 |

# Função dos Componentes
**• Transformador:** O transformador é o componente responsável por diminuir a tensão de entrada do circuito para um valor mais próximo ao desejado. O transformador utilizado reduz a tensão de pico de 127V para uma de, aproximadamente, 18V. Nota-se que esta ainda não é a tensão exigida para o projeto, portanto o restante do circuito é moldado para que a tensão de saída permaneça no intervalo 3-12V.<br><br>
**• Ponte de Diodos:** Os diodos são componentes que permitem o fluxo unidirecional de corrente. Quando organizados na forma de ponte de diodos, atuam para manter o abastecimento de corrente em ambas as fases do fornecimento de tensão (semiciclo positivo e negativo). Após essa etapa, a voltagem é retificada (polaridade única) e torna-se pulsante.<br><br>
**• Capacitor:** Um capacitor armazena carga elétrica até determinada quantia, a depender da capacitância, após a qual esta carga é liberada. No circuito, o capacitor é responsável por filtrar a voltagem, reduzindo a amplitude da pulsação. A voltagem resultante assume a forma de um Ripple.<br><br>
**• Diodo Zener:** Um Diodo Zener, quando instalado no sentido da corrente, assim como um diodo normal, permite o fluxo unidirecional de corrente. Quando instalado no sentido contrário, atua como um retificador de tensão. Na fonte, o Zener é instalado no sentido reverso, portanto retifica a tensão para um valor constante, neste caso, de 13V.<br><br>
**• Transistor:** O transistor é um componente semicondutor capaz de amplificar ou atenuar a passagem da corrente elétrica pelo circuito. Esse dispositivo possui três terminais, os quais, na configuração NPN, têm as seguintes funções: base, responsável por controlar a corrente que flui entre o coletor e o emissor; emissor, local por onde a corrente elétrica entra; e coletor, terminal que libera a corrente de saída. Sob a perspectiva do projeto, o ganho entre a corrente da base (Ib) e do coletor (Ic) é de, aproximadamente, cem vezes, possibilitando a existência da corrente elétrica desejada de 100mA na saída.<br><br>
**• Potenciômetro:** O potenciômetro é um componente com uma resistência variável. A resistência máxima do potenciômetro empregado é de 5kΩ, e sua função é regular, conforme a resistência aplicada, a tensão de saída do circuito (resistência mínima ---> 3V / resistência máxima ---> 12V).<br><br>
**• Resistores:** Resistores consomem tensão quando associados em série, e para limitar corrente quando ligados em paralelo. Neste caso, contribuem para auxiliar o circuito a atingir as exigências de corrente e tensão.<br><br>
**• LED:** Esse dispositivo indica a passagem de corrente onde foi instalado, então foi inserido para acusar o funcionamento da fonte para o usuário.<br><br>

# Circuito da Fonte
![Circuito_Falstad](https://github.com/user-attachments/assets/3bb7d7d2-5d10-4e19-87b2-a835b187d8c1)
[Link do Circuito no falstad](https://tinyurl.com/24vk4z9p)

# EAGLE - Esquemático do Circuito 
![Captura de tela 2025-06-30 124237](https://github.com/user-attachments/assets/24ba83f2-6280-4b36-9aa0-ae69ad864b10)

# EAGLE - Placa de Circuito Impresso (PCB)
![Captura de tela 2025-06-30 123709](https://github.com/user-attachments/assets/60632ac7-e16a-44ed-ab8f-14e5c72a1496)

# Cálculos

**• Razão das Espiras do transformador:** Para esse cálculo, utilizamos a fórmula: Vp/Vs = Np/Ns, sendo Np = Número de espiras no primário e Ns o número de espiras no secundário. Assim, temos: 127/18 ≈ 7,05

**• Tensão de Pico:** A tensão inicial foi de 127V, logo, a tensão de pico é 127 * √2 ≈ **179,6V**

**• Tensão total no capacitor:** Para isso, vamos calcular a tensão de pico utilizando tensão da bobina secundária (18V), 18 * √2 ≈ **25,45V**, essa seria a tensão ideal.
Após isso, para calcular a tensão total do capacitor, temos que considerar as perdas do diodo, Vp - Vperdida = 25,45 - (2 * 0,7V) = **24,05V** 

**• Tensão no ripple e capacitância:** Para a tensão de ripple, vamos limitá-lo a 10% da tensão do circuito, sendo assim: Vripple : Vtotal * 0,10 = 24,05 * 0,1 = **2,405V**
Agora consideraremos a fórmula para calcular a capacitância: C = I / 2 * f * V; Nesse caso, temos I como corrente total do circuito (≈102mA), f = frequência de 60Hz, da tomada e V, que nesse caso vamos utilizar o Vripple calculado anteriormente. Com isso, a conta fica: C = 102 * 10^-3 / 2 * 60 * 2,405 ≈ **353 * 10^-6 F ou 353μF**.

**• Diodo Zener:** Resistência do diodo zener: Para esse cálculo, utilizaremos valores conhecidos do circuito, sendo a potência do zener (1W) e a tensão do zener(13V), usando a fórmula Pot = U * I. Isolando para I, temos: I = Pot / U -> I = 1 / 13  ≈ **77mA**

A fonte fornece 24,05V, e a saída precisa ser 13V(Tensão do Zener), logo a queda de tensão é de 11,05V. COm isso, para calcular a resistência mínima para ter essa tensão é preciso fazer : U = R * I -> R = U / I -> R = 11,05 / 77 * 10^-3 =  **143,5Ω**    

Agora para a resistência máxima: R * Imax = (Vtotal - Vripple) - Vzener -> R * Imax = 24,05 - 2,405 - 13 = 8,645V. Assim, podemos calcular Imax por : Ic + Iz + Ir, sendo Ic a corrente depois do pontênciometro (1mA), Iz a corrente que passa pelo Zener, como estamos calculando o caso de resistência máxima, a corrente do zener é 0. E por fim, o Ir que é a corrente que passa pelo resistor de 2,2K, abaixo do potenciometro (1,8mA, valor mostrado pelo Falstad)
Assim, podemos dizer que Imax = 1mA + 0 + 1,8mA = **2,8mA**.  

Agora, temos tudo o que precisamos para calcular a resistência máxima -> R * Imax = 8,645V -> R = 8,645 / 2,8 * 10^-3 -> Rmax = **3087Ω ou 3,087KΩ**


