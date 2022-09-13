# Como escrever comentários de revisão de código

## Resumo

- Seja amável.
- Explique seu raciocínio.
- Equilibre entre dar instruções explícitas e apenas apontar problemas deixando o desenvolvedor decidir.
- Incentive os desenvolvedores a simplificar o código ou adicionar comentários no código em vez de apenas explicar a complexidade para você.

## Cortesia

Em geral, é importante ser [cortês e respeitoso](https://chromium.googlesource.com/chromium/src/+/master/docs/cr_respect.md) além de ser muito claro e útil para o desenvolvedor cujo código você está revendo. Uma maneira de fazer isso é ter certeza de que você está sempre fazendo comentários sobre o _código_ e nunca fazendo comentários sobre o _desenvolvedor_. Você não precisa sempre seguir essa prática, mas você definitivamente deve usar isso dizendo algo que poderia ser perturbador ou controverso. Por exemplo:

Ruim: "Por que **você** usou threads aqui quando obviamente não há nenhum benefício em ter ganho com concorrência?"

Bom: "Pelo que eu posso ver, o modelo de concorrência aqui está adicionando complexidade ao sistema sem qualquer benefício real de desempenho. Por não haver benefício em desempenho, é melhor que este código seja de thread única em vez de usar vários tópicos."

## Explique Por Que {#why}

Uma coisa que você notará sobre o "bom" exemplo acima é que ele ajuda o desenvolvedor a entender _por que_ você está fazendo seu comentário. Você nem sempre precisa incluir essas informações nos comentários da sua avaliação, mas às vezes é apropriado para dar um pouco mais de explicação sobre sua intenção, sobre a melhor prática que você está seguindo, ou como sua sugestão melhora a saúde do código.

## Dando Orientação {#guidance}

**Em geral, é responsabilidade do desenvolvedor corrigir uma CL, não dos revisores.**
Você não é obrigado a fazer detalhadamente o design da solução ou escrever cada código para o desenvolvedor.

Isso não significa que o revisor não seja útil, muito pelo contrário. Em geral você deve encontrar um equilíbrio adequado entre apontar problemas e fornecer orientação direta. Apontando problemas e deixando o desenvolvedor tomar as decisões, muitas vezes ajuda o desenvolvedor a aprender e torna mais fácil fazer revisões de código. Isso também pode resultar em uma solução melhor, pois o desenvolvedor está mais próximo do código do que o revisor.

No entanto, algumas vezes, instruções diretas, sugestões ou mesmo código são mais úteis. O objetivo principal da revisão de código é obter a melhor CL possível. Um objetivo secundário é melhorar as habilidades dos desenvolvedores para que eles exijam menos e menos revisão ao longo do tempo.

Lembre-se de que as pessoas aprendem com o reforço do que estão fazendo bem e não apenas o que eles poderiam fazer melhor. Se você vê coisas que gosta na CL, comenta aí também! Exemplos: desenvolvedor limpou um algoritmo confuso, adicionando uma cobertura de teste exemplar, ou você, como revisor, aprendeu algo com a CL. Assim como em todos os comentários, inclua [por que](#why) você gostou de algo e incentive o desenvolvedor a continuar as boas práticas.

## Aceitando explicações {#explanations}

Se você pedir a um desenvolvedor para explicar um código que você não entende, isso geralmente deve resultar em **reescrever o código de forma mais clara**. Ocasionalmente, adicionar um comentário no código também é uma resposta apropriada, contanto que não esteja apenas excesivamente explicando um código mais complexo.

**As explicações escritas apenas na ferramenta de revisão de código não são úteis para futuros leitores de código.** Elas apenas são aceitáveis em algumas circunstâncias, como quando você está revisando uma área com a qual não está muito familiarizado e o desenvolvedor explica algo que os leitores normais do código já saberiam.

Next: [Handling Pushback in Code Reviews](pushback.md)

Próximo: [Como Lidar com Negativas nas Revisões de Código](pushback.md)
