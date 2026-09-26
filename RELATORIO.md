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
Crie um registro "PathState" que armazena altura, yaw, pitch, e posição 2d de um determinado coelho em um determinado momento no mapa em uma determinada trajetória. Após isso, crie variáveis globais para armazenar informações dos três diferentes caminhos que os coelhos podem seguir. As variáveis e os valores exatos que utilizei estão em [aqui](GLOBALS.md) Depois, crie uma função para cada tipo de movimento. Prompts úteis para criá-las podem ser conferios [nesse arquivo](PROMPTS.md) 
</mark>

## Principais dificuldades encontradas durante o desenvolvimento (formato livre)

<mark>`<preencher>`</mark>

## Você acha que conseguiu resolver o problema de forma adequada?

<mark> Em um geral, creio que consegui reproduzir os movimentos dos coelhos do vídeo apropriadamente por intermédio de transformações geométricas. No entanto, houve alguns detalhes mais minuciosos os quais não consegui reproduzir, como a virada contínua dos coelhos verdes do caminho em formato de retângulo: quando um coelho chega a um vértice da figura e vira para tornar a andar ao longo do próximo lado do retângulo, essa virada é brusca (i.e. o seu vetor de direção passa a instantaneamente assumir a mesma direção do novo lado), algo que no vídeo de referência ocorre de forma contínua e suavizada (um movimento mais natural). Uma suposição minha para reproduzir tal efeito seria fazer com que as figuras dos animais sigam o formato de um retângulo com bordas arredondadas (i.e. ao invés de vértices, as bordas do retângulo são setores circulares) </mark>

## Se você quiser compartilhar mais alguma coisa, coloque aqui:

<mark> Não disponho de nenhuma informação adicional. </mark>

## Se você possui alguma sugestão para o professor sobre esta atividade, coloque aqui:

<mark> Não tenho nenhuma sugestão. Julgo o trabalho bem especificado e explicado. </mark>
