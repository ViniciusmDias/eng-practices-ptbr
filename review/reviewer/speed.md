# Velocidade das Revisões de Código

## Por Que as Revisões de Código Devem Ser Rápidas? {#why}

**No Google, otimizamos a velocidade com que uma equipe de desenvolvedores podem produzir um produto juntos**, em vez de otimizar a velocidade com que um desenvolvedor individual pode escrever código. A velocidade do desenvolvimento individual é importante, mas não é tão importante _quanto_ a velocidade de toda a equipe.

Quando as revisões de código são lentas, várias coisas acontecem:

- **A velocidade da equipe como um todo diminui.** Sim, o indivíduo que não responde rapidamente à revisão, vai fazer outro trabalho. No entanto, novos recursos e correções de bugs para o resto da equipe estão atrasados por dias, semanas, ou meses enquanto cada CL aguarda por revisões e re-revisões.

- **Os desenvolvedores começam a protestar contra o processo de revisão de código.** Se apenas um revisor responde a cada poucos dias, mas solicita grandes alterações na CL a cada vez, isto pode ser frustrante e difícil para os desenvolvedores. Muitas vezes, isso é expresso com reclamções sobre o quão "rigoroso" o revisor está sendo. Se o revisor solicita as _mesmas_ mudanças substanciais (mudanças que realmente melhoram a saúde do código) mas responde _rapidamente_ toda vez que o desenvolvedor faz uma atualização, as reclamaçoes tendem a desaparecer. **A maioria das reclamações sobre o processo de revisão de código são realmente resolvidas apenas tornando o processo mais rápido.**

- **A saúde do código pode ser afetada.** Quando as revisões são lentas, há um aumento de pressão para permitir que os desenvolvedores enviem as CLs que não sejam tão boas quanto elas poderiam ser. Revisões lentas também desencorajam limpezas de código, refatorações e melhorias adicionais nas CLs existentes.

## Quão Rápidas Devem Ser as Revisões de Código? {#fast}

Se você não estiver focado no meio de uma tarefa, **você deve fazer uma revisão de código antes de começar uma.**

**Um dia útil é o tempo máximo necessário para responder** a um código que solicitou uma revisão (ou seja, logo na manhã seguinte).

Seguir essas diretrizes significa que uma CL típica deve receber várias rodadas de revisão (se necessário) em um único dia.

## Velocidade vs. Interrupção {#interruption}

Existe um momento em que a consideração da velocidade pessoal supera a velocidade da equipe. **Se você estiver focado no meio de uma tarefa, como escrever código, não se interrompa para fazer uma revisão de código.** A pesquisa mostrou que pode levar muito tempo para um desenvolvedor voltar a um fluxo suave de desenvolvimento após ser interrompido. Então, se interromper durante a codificação é na verdade _mais_ caro para a equipe do que fazer outro desenvolvedor esperar um pouco por uma revisão de código.

Em vez disso, aguarde um ponto de interrupção em seu trabalho antes de responder a uma solicitação de revisão. Isso pode acontecer quando sua tarefa de codificação atual estiver concluída, após o almoço, voltando de uma reunião, voltando da sala de descanso, etc.

## Respostas Rápidas {#responses}

Quando falamos sobre a velocidade das revisões de código, é o tempo de _resposta_ que estamos preocupados, ao contrário do tempo de quanto leva para uma CL passar pela revisão completa e ser submetido ao código. É ideal também que todo o processo seja rápido, mas **é ainda mais importante que as _respostas individuais_ aconteçam rapidamente do que todo o processo em si acontecer rapidamente.**

Mesmo que às vezes leve muito tempo para passar por todo o _processo_ de revisão, tendo respostas rápidas do revisor durante todo o processo alivia significativamente a frustração que os desenvolvedores podem sentir com as lentas revisões de código.

If you are too busy to do a full review on a CL when it comes in, you can still
send a quick response that lets the developer know when you will get to it,
suggest other reviewers who might be able to respond more quickly, or
[provide some initial broad comments](navigate.md). (Note: none of this means
you should interrupt coding even to send a response like this&mdash;send the
response at a reasonable break point in your work.)

Se você estiver muito ocupado para fazer uma revisão completa em uma CL quando ela chegar ainda poderá enviar uma resposta rápida que permita ao desenvolvedor saber quando você irá revisar, sugerir outros revisores que possam responder mais rapidamente, ou [forneça alguns comentários amplos iniciais](navigae.md). (Nota: nada disso significa que você deve interromper a codificação mesmo para enviar uma resposta como esta &mdash; envie a resposta em uma pausa em seu trabalho.)

**It is important that reviewers spend enough time on review that they are
certain their "LGTM" means "this code meets [our standards](standard.md)."**
However, individual responses should still ideally be [fast](#fast).

**É importante que os revisores gastem tempo suficiente na revisão para que seja certo que seu "LGTM" signifique "este código atende [nossos padrões](standard.md)."**
No entanto, as respostas individuais ainda devem ser [rápidas](#fast).

## Cross-Time-Zone Reviews {#tz}

## Avaliações Entre Fuso Horários {#tz}

When dealing with time zone differences, try to get back to the author while
they have time to respond before the end of their working hours. If they have
already finished work for the day, then try to make sure your review is done
before they start work the next day.

Ao lidar com diferenças de fuso horário, tente responder ao autor enquanto eles têm tempo para responder antes do final de suas horas de trabalho. Se eles ja terminaram o trabalho do dia, então tente certificar-se de que sua revisão foi feita antes de começar a trabalhar no dia seguinte.

## LGTM With Comments {#lgtm-with-comments}

## LGTM Com Comentários {#lgtm-with-comments}

In order to speed up code reviews, there are certain situations in which a
reviewer should give LGTM/Approval even though they are also leaving unresolved
comments on the CL. This is done when either:

Para acelerar as revisões de código, existem certas situações em que um revisor deve dar LGTM/Aprovação mesmo que eles também estejam deixando sem solução comentários sobre o CL. Isso é feito quando:

- The reviewer is confident that the developer will appropriately address all
  the reviewer's remaining comments.

- O revisor está confiante de que o desenvolvedor abordará adequadamente todos os comentários restantes do revisor.

- The remaining changes are minor and don't _have_ to be done by the
  developer.

- As alterações restantes são pequenas e não _tem_ que ser feitas pelo desenvolvedor.

The reviewer should specify which of these options they intend, if it is not
otherwise clear.

O revisor deve especificar qual dessas opções escolheu, se não estiver claro.

LGTM With Comments is especially worth considering when the developer and
reviewer are in different time zones and otherwise the developer would be
waiting for a whole day just to get "LGTM, Approval."

Vale a pena considerar o LGTM com comentários especialmente quando o desenvolvedor e revisor estão em fusos horários diferentes e, caso contrário, o desenvolvedor ficaria esperando um dia inteiro apenas para obter "A aprovação por, LGTM."

## Large CLs {#large}

## CLs grandes {#large}

If somebody sends you a code review that is so large you're not sure when you
will be able to have time to review it, your typical response should be to ask
the developer to
[split the CL into several smaller CLs](../developer/small-cls.md) that build on
each other, instead of one huge CL that has to be reviewed all at once. This is
usually possible and very helpful to reviewers, even if it takes additional work
from the developer.

Se alguém lhe enviar uma revisão de código tão grande que você não tenha certeza de quando terá tempo para revisá-lo, sua resposta típica deve ser pedir para o desenvolvedor [dividir a CL em várias CLs menores](../developer/small-cls.md) que se baseiam uns nos outros, em vez de uma enorme CL que precisa ser revisado de uma só vez. Isto é geralmente possível e muito útil para os revisores, mesmo que exija trabalho adicional do desenvolvedor.

If a CL _can't_ be broken up into smaller CLs, and you don't have time to review
the entire thing quickly, then at least write some comments on the overall
design of the CL and send it back to the developer for improvement. One of your
goals as a reviewer should be to always unblock the developer or enable them to
take some sort of further action quickly, without sacrificing code health to do
so.

Se uma CL _não puder_ ser dividida em CLs menores e você não tiver tempo para revisar a coisa toda rapidamente, então pelo menos escreva de volta alguns comentários gerais sobre o design da CL ao desenvolvedor para melhoria. Um dos seus objetivos como um revisor deve ser sempre desbloquear o desenvolvedor ou permitir que ele tome alguma ação adicional rapidamente, sem sacrificar a saúde do código para fazer isso.

## Code Review Improvements Over Time {#time}

## Melhorias na Revisão de Código ao Longo do Tempo {#time}

If you follow these guidelines and you are strict with your code reviews, you
should find that the entire code review process tends to go faster and faster
over time. Developers learn what is required for healthy code, and send you CLs
that are great from the start, requiring less and less review time. Reviewers
learn to respond quickly and not add unnecessary latency into the review
process.
But **don't compromise on
the [code review standards](standard.md) or quality for an imagined improvement
in velocity**&mdash;it's not actually going to make anything happen more
quickly, in the long run.

Se você seguir essas diretrizes e for rigoroso com suas revisões de código, você deve descobrir que todo o processo de revisão de código tende a ser cada vez mais rápido conforme o tempo passa. Os desenvolvedores aprendem o que é necessário para manter o código íntegro e enviam para você CLs que são boas desde o começo, exigindo cada vez menos tempo de revisão. Revisores aprendem a responder rapidamente e não adicionar latência desnecessária ao processo de revisão. Mas **não comprometa os [padrões de revisão de código](standard.md) ou a qualidade para imaginada melhoria na velocidade** &mdash; Na verdade, isso não vai acontecer mais rapidamente, a longo prazo.

## Emergencies

## Emergências

There are also [emergencies](../emergencies.md) where CLs must pass through the
_whole_ review process very quickly, and where the quality guidelines would be
relaxed. However, please see [What Is An Emergency?](../emergencies.md#what) for
a description of which situations actually qualify as emergencies and which
don't.

Existem também [emergências](../emergencies.md) onde os CLs devem passar por _todo_ processo de revisão muito rapidamente e onde as diretrizes de qualidade seriam diminuidas. No entanto, consulte [O Que é Uma Emergência?](../emergencies.md#o-que-é-uma-emergência-what) para uma descrição de quais situações realmente se qualificam como emergências e quais não.

Next: [How to Write Code Review Comments](comments.md)

Próximo: [Como Escrever Comentários de Revisão de Código](comments.md)
