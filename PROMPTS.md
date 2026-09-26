# Definição das Funções para cada um dos três tipos de movimentação (retangular, em losango e ciruclar)

## Movimento Retangular (Área verde da bandeira)

<mark>
Na função de movimento retangular, calcule a distância total já percorrida (speed*time) usando módulo com o perímetro para repetir o loop (d = fmodf(speed * time, perimeter);). Também determine em qual dos lados o objeto está e calcule a fração já percorrida daquele segmento (t) bem como o vetor direção nele. Na sequência, interpole linearmente a posição entre os dois extremos do segmento atual. Calcule a altura do salto usando a função seno em função de t (state.height   = g_HopHeight * sinf(pi*t);), o que gera o moviento de arco (zero nas extremidades e máximo no meio). Ademais, com o vetor direção, calcule o yaw usando atan2(). Por fim, calcule o pitch com a derivada de height em relação à distância percorrida (máxima nas bordas e nula no meio do segmento).
</mark>


## Movimento em Losango (Área amarela da bandeira)
<mark>
Utilize a mesma lógica de retornar um PathState e de cálculo de posição, pitch, yaw e altura que foi aplicada no cálculo da trajetória ao longo do retângulo. No entanto, como os lados dessa figuram geométrica não formam 90 graus entre si e podem estar dispostas em qualquer direção do terreno (i.e. não exatamente sobre eixos globais x,z), o cálculo de direção e posição deve ser levemente alterado: O losango tem 4 vértices, definidos pelas metades das diagonais diagX e diagZ:
direita (diagX/2, 0), frente (0, diagZ/2), esquerda (-diagX/2, 0), trás (0, -diagZ/2). Assim, Calcule o comprimento de cada um dos 4 lados dinamicamente, como a distância euclidiana entre vértices consecutivos (glm::length).

Dada a distância total percorrida (via fmodf do tempo * velocidade pelo perímetro), descubra em qual dos 4 lados o objeto está atualmente, usando um laço (não um if/else fixo, já que os lados podem ter comprimentos diferentes entre si dependendo de diagX e diagZ). A direção do movimento naquele lado deve ser calculada como o vetor normalizado entre os dois vértices daquele lado (glm::normalize(b - a)). Já a posição segue sendo a interpolação linear entre os dois vértices do segmento em questão.
</mark>


## Movimento Circular (Área azul da bandeira)
<mark>
No cálculo da trajetória circular, calcule a velocidade angular omega e o deslocamento angular theta por meio das grandezas equivalentes escalares. Use a mesma lógica para o cálculo de yaw, pitch, e height que aquela que utilizamos nas funções de trajetória anteriores. No entanto a posição é dada por uma parametrização do círculo em tempo real state.position = (radius*sin(theta), radius*cos(theta)) (e não por uma interpolação discreta, como era nos casos anteriores). Já O vetor direção nesse caso (ainda utilizado para calcular yaw) é simplesmente a derivada do movimento (ou seja, o vetor velocidade) (cos(theta),-sin(theta)) normalizado (de nada importa a escala). Como uma circunferências não tem vértices e lados definidos, utilizaremos uma segmentação artificial dela para atribuir valores de t para o cálculo do seno que dará o movimento de pulos senoidais. Para tal, utilize o seguinte código:
       segment_length = circumference / numHops;
       d = fmodf(speed * time, segment_length);
       t = d / segment_length;
</mark>