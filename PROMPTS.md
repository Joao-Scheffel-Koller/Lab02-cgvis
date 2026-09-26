# Definição das Funções para cada um dos três tipos de movimentação (retangular, em losango e ciruclar)

## Movimento Retangular (Área verde da bandeira)

<mark>
Na função de movimento retangular, calcule a distância total já percorrida (speed*time) usando módulo com o perímetro para repetir o loop (d = fmodf(speed * time, perimeter);). Também determine em qual dos lados o objeto está e calcule a fração já percorrida daquele segmento (t) bem como o vetor direção nele. Na sequência, interpole linearmente a posição entre os dois extremos do segmento atual. Calcule a altura do salto usando a função seno em função de t (state.height   = g_HopHeight * sinf(pi*t);), o que gera o moviento de arco (zero nas extremidades e máximo no meio). Ademais, com o vetor direção, calcule o yaw usando atan2(). Por fim, calcule o pitch com a derivada de height em relação à distância percorrida (máxima nas bordas e nula no meio do segmento).
</mark>


## Movimento em Losango (Área amarela da bandeira)
<mark>

</mark>


## Movimento Circular (Área azul da bandeira)
<mark>
</mark>