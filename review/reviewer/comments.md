# How to write code review comments

# Como escrever comentários de revisão de código

## Summary

## Resumo

- Be kind.
- Explain your reasoning.
- Balance giving explicit directions with just pointing out problems and
  letting the developer decide.
- Encourage developers to simplify code or add code comments instead of just
  explaining the complexity to you.

- Seja amável.
- Explique seu raciocínio.
- Equilibrar entre dar instruções explícitas e apenas apontar problemas deixando o desenvolvedor decidir.
- Incentive os desenvolvedores a simplificar o código ou adicionar comentários no código em vez de apenas explicar a complexidade para você.

## Courtesy

## Cortesia

In general, it is important to be
[courteous and respectful](https://chromium.googlesource.com/chromium/src/+/master/docs/cr_respect.md)
while also being very clear and helpful to the developer whose code you are
reviewing. One way to do this is to be sure that you are always making comments
about the _code_ and never making comments about the _developer_. You don't
always have to follow this practice, but you should definitely use it when
saying something that might otherwise be upsetting or contentious. For example:

Em geral, é importante ser [cortês e respeitoso](https://chromium.googlesource.com/chromium/src/+/master/docs/cr_respect.md) além de ser muito claro e útil para o desenvolvedor cujo código você está revendo. Uma maneira de faer isso é ter certeza de que você está sempre fazendo comentários sobre o _código_ e nunca fazendo comentários sobre o _desenvolvedor_. Você não precisa sempre seguir essa prática, mas você definitivamente deve usar isso dizendo algo que poderia ser perturbador ou controverso. Por exemplo:

Bad: "Why did **you** use threads here when there's obviously no benefit to be
gained from concurrency?"

Ruim: "Por que **você** usou threads aqui quando obviamente não há nenhum benefício em ter ganho com concorrência?"

Good: "The concurrency model here is adding complexity to the system without any
actual performance benefit that I can see. Because there's no performance
benefit, it's best for this code to be single-threaded instead of using multiple
threads."

Bom: "Pelo que eu posso ver, o modelo de concorrência aqui está adicionando complexidade ao sistema sem qualquer benefício real de desempenho. Porque não haver benefício em desempenho, é melhor que este código seja de thread única em vez de usar vários tópicos."

## Explain Why {#why}

## Explique por que {#por que}

One thing you'll notice about the "good" example from above is that it helps the
developer understand _why_ you are making your comment. You don't always need to
include this information in your review comments, but sometimes it's appropriate
to give a bit more explanation around your intent, the best practice you're
following, or how your suggestion improves code health.

Uma coisa que você notará sobre o "bom" exemplo acima é que ele ajuda o desenvolvedor a entender _por que_ você está fazendo seu comentário. Você nem sempre precisa incluir essas informações nos comentários da sua avaliação, mas às vezes é apropriado para dar um pouco mais de explicação sobre sua intenção, sobre a melhor prática que você está seguindo, ou como sua sugestão melhora a saúde do código.

## Giving Guidance {#guidance}

## Orientando {#guidance}

**In general it is the developer's responsibility to fix a CL, not the
reviewer's.** You are not required to do detailed design of a solution or write
code for the developer.

**Em geral, é responsabilidade do desenvolvedor corrigir uma CL, não dos revisores.**
Você não é obrigado a fazer detalhadamente o design da solução ou escrever cada código para o desenvolvedor.

This doesn't mean the reviewer should be unhelpful, though. In general you
should strike an appropriate balance between pointing out problems and providing
direct guidance. Pointing out problems and letting the developer make a decision
often helps the developer learn, and makes it easier to do code reviews. It also
can result in a better solution, because the developer is closer to the code
than the reviewer is.

Isso não significa que o revisor deva ser inútil, muito pelo contrário. Em geral você deve encontrar um equilíbrio adequado entre apontar problemas e fornecer orientação direta. Apontando problemas e deixando o desenvolvedor tomar as decisões, muitas vezes ajuda o desenvolvedor a aprender e torna mais fácil fazer revisões de código. Isso também pode resultar em uma solução melhor, pois o desenvolvedor está mais próximo do código do que o revisor.

However, sometimes direct instructions, suggestions, or even code are more
helpful. The primary goal of code review is to get the best CL possible. A
secondary goal is improving the skills of developers so that they require less
and less review over time.

No entanto, algumas vezes, instruções diretas, sugestões ou mesmo código são mais úteis. O objetivo principal da revisão de código é obter a melhor CL possível. Um objetivo secundário é melhorar as habilidades dos desenvolvedores para que eles exijam menos e menos revisão ao longo do tempo.

Remember that people learn from reinforcement of what they are doing well and
not just what they could do better. If you see things you like in the CL,
comment on those too! Examples: developer cleaned up a messy algorithm, added
exemplary test coverage, or you as the reviewer learned something from the CL.
Just as with all comments, include [why](#why) you liked something, further
encouraging the developer to continue good practices.

Lembre-se de que as pessoas aprendem com o reforço do que estão fazendo bem e não apenas o que eles poderiam fazer melhor. Se você vê coisas que gosta na CL, comenta aí também! Exemplos: desenvolvedor limpou um algoritmo confuso, adicionando uma cobertura de teste exemplar, ou você, como revisor, aprendeu algo com a CL. Assim como em todos os comentários, inclua [por que](#why) você gostou de algo e incentive o desenvolvedor a continuar as boas práticas.

## Accepting Explanations {#explanations}

## Aceitando explicações

If you ask a developer to explain a piece of code that you don't understand,
that should usually result in them **rewriting the code more clearly**.
Occasionally, adding a comment in the code is also an appropriate response, as
long as it's not just explaining overly complex code.

Se você pedir a um desenvolvedor para explicar um código que você não entende, isso geralmente deve resultar em **reescrever o código de forma mais clara**.

**Explanations written only in the code review tool are not helpful to future
code readers.** They are acceptable only in a few circumstances, such as when
you are reviewing an area you are not very familiar with and the developer
explains something that normal readers of the code would have already known.

**As explicações escritas apenas na ferramenta de revisão de código não são úteis para futuros leitores de código.** Eles apenas são aceitáveis em algumas circunstâncias, como quando você está revisando uma área com a qual não está muito familiarizado e o desenvolvedor explica algo que os leitores normais do código já saberiam.

Next: [Handling Pushback in Code Reviews](pushback.md)

Próximo: [Como Lidar Negativas nas Revisões de Código](pushback.md)
