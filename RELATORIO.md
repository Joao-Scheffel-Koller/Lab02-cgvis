# Relatório - Coelinhos do Brasil

> [!CAUTION]
> - Lembre-se que você <ins>**não pode utilizar ferramentas de IA para
>   escrever este relatório**</ins>

## Dados do aluno

- **Cartão UFRGS**: <mark>00589701</mark>
- **Nome**: <mark>João Luis Scheffel Koller</mark>

## Passos que eu segui para resolver o problema especificado (em formato de *"prompt"*)

> [!IMPORTANT]
> - Coloque aqui todas as informações necessárias para que alguém
>   (pessoa ou ferramenta de IA) possa reproduzir os seus passos para
>   solucionar o problema
> - Escreva em formato imperativo, como se fosse um *prompt* com as
>   instruções a serem seguidas na solução do problema
> - Seja objetivo e conciso: quanto *menos palavras* você utilizar,
>   melhor
> - Seja técnico e use terminologia adequada: assuma que quem irá ler
>   os seus passos possui conhecimento de Ciência da Computação e
>   Computação Gráfica
> - Caso você queira incluir informações "longas" (como algum *prompt*
>   grande usado com alguma ferramenta de IA), crie arquivos à parte e
>   adicione links no texto (por exemplo, crie o arquivo `PROMPTS.md`
>   e adicione um link markdown `[os prompts detalhados estão
>   aqui](PROMPTS.md)`)
> - Novamente, lembre-se que você *não pode utilizar ferramentas
>   de IA para escrever este relatório*

<mark>
> - Crie um registro "PathState" que armazena altura, yaw, pitch, e posição 2d de um determinado coelho em um determinado >momento no mapa em uma determinada trajetória. 
>
> - Após isso, crie variáveis globais para armazenar informações dos três diferentes caminhos que os coelhos podem seguir (e.>g. raio do círculo). As variáveis e os valores exatos que utilizei estão [aqui](GLOBALS.md) 
>
> - Depois, crie uma função para cada tipo de movimento. Prompts úteis para definí-las em seus pormenores podem ser >conferidos [nesse arquivo](PROMPTS.md). 
>
> - Para renderizar os coelhos seguindo uma mesma trajetória defasados no tempo (efeito trem) calcule no laço while >principal (!WindowShouldClose())para cada coelho i de cada grupo (retângulo, losango, círculo) o seu PathState na >trajetória (posição, altura, pitch e yaw) com a sua função respectiva (definida conforme [PROMPTS.md](PROMPTS.md)) >utilizando como tempo "bunny_time = current_time - i * bunnyTimeLag" (sendo bunnyTimeLag um número de sua escolha para >espaçar temporalmente as figuras). Assim, a matriz de modelagem da figura em questão deve ser equivalente a uma rotação >PathState.pitch unidades no eixo z (inclinar nariz conforme subida no arco) seguida de uma rotação PathState.yaw unidades >no eixo y (olhar para o sentido de movimento) e uma translação para a posição calculada (PathState.position.x, state.>height, PathState.position.y) (deslocamento na trajetória respectiva). Não se esqueça de utilizar as cores JADE_SURFACE,>GOLD_SURFACE e BLUE_PLASTIC_SURFACE de acordo com o grupo em questão para formar a bandeira corretamente.
>
> - Dentro do mesmo laço for que itera sobre cada coelho de cada grupo, desenhe a boina (que é o objeto de esfera distorcido >com uma matriz scale para ficar mais "achatado") sobre a cabeça de cada animal: Basta utilizar a mesma matriz model do >coelho como base, de modo que herde automaticamente posição, yaw e pitch daquele instante e aplicar uma matriz de >translação >(para que a boina não fique no centro do coelho, mas sobre a sua cabeça).
>
> - Por fim, não se esqueça de aumentar o terreno e o far plane para cobrirem a área das trajetórias. Para o primeiro, basta >aumentar os valores de x e z na matriz de scale que é utilizada para formar a matriz de modelagem do terreno quando este é >renderizado. Já para o segundo, altere diretamente a variáavel farplane para um número maior desejado.</mark>

## Principais dificuldades encontradas durante o desenvolvimento (formato livre)

<mark> Naturalmente, a primeira dificuldade que tive foi de compreender o funcionamento do código, já que essa foi a minha primeira vez lidando com openGL. Outra dificuldade marcante que enfrentei foi a de encontrar a solução correta para calcular a trajetória em formato de losango (A solução encontrada também serviria ao retângulo, já que ambos possuem mesma topologia), já que os lados do losango possuem ângulos entre si diferentes de 90 graus. Por fim, uma solução simples, mas cuja ideia eu demorei a ter foi a  de renderizar os coelhos em tempos defasados para gerar o efeito trem. Logo de início, meu código fazia com que os coelhos andassem sempre juntos pois eu não adicionava um lag entre eles.</mark>

## Você acha que conseguiu resolver o problema de forma adequada?

<mark> Em um geral, creio que consegui reproduzir os movimentos dos coelhos do vídeo apropriadamente por intermédio de transformações geométricas. No entanto, houve alguns detalhes mais minuciosos os quais não consegui reproduzir, como a virada contínua dos coelhos verdes do caminho em formato de retângulo: quando um coelho chega a um vértice da figura e vira para tornar a andar ao longo do próximo lado do retângulo, essa virada é brusca (i.e. o seu vetor de direção passa a instantaneamente assumir a mesma direção do novo lado), algo que no vídeo de referência ocorre de forma contínua e suavizada (um movimento mais natural). Uma suposição minha para reproduzir tal efeito seria fazer com que as figuras dos animais sigam o formato de um retângulo com bordas arredondadas (i.e. ao invés de vértices, as bordas do retângulo são setores circulares) </mark>

## Se você quiser compartilhar mais alguma coisa, coloque aqui:

<mark> Não disponho de nenhuma informação adicional. </mark>

## Se você possui alguma sugestão para o professor sobre esta atividade, coloque aqui:

<mark> Não tenho nenhuma sugestão. Julgo o trabalho bem especificado e explicado. </mark>
