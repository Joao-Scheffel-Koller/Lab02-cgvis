# Parâmetros utilizados para modelar os 3 tipos de caminhos (em retângulo, losango ou círculo) e a movimentaçção dos coelhos

## Valor de Pi truncado padronizado

<mark> float pi = 3.14159265f; </mark>

## Números de Coelhos por trilha

<mark>
int squareBunnyNumber = 24;
int circleBunnyNumber = 8;
int rhombusBunnyNumber = 14; 
</mark>

## Variáveis globais do caminho retangular

<mark>
float squareWidth = 15.0f;
float squareDepth = 21.0f;
float g_SquarePathSpeed = 4.0f; 
float g_HopHeight = 1.4f; 


float perimeter = (2.0f * squareWidth) + (2.0f * squareDepth);
float total_lap_time = perimeter / g_SquarePathSpeed;
float bunnyTimeLag = total_lap_time / squareBunnyNumber;
</mark>

## Variáveis do caminho circular

<mark>
float circleRadius = 2.5f;
float circleSpeed = g_SquarePathSpeed;
float numHops = 8;
</mark>

## Variáveis do caminho em losango

<mark>
float rhombusDiagZ = 17.5f;
float rhombusDiagX = 10.0f;
float rhombusSpeed = g_SquarePathSpeed;
</mark>