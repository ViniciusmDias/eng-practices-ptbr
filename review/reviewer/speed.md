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

Se você estiver muito ocupado para fazer uma revisão completa em uma CL quando ela chegar ainda poderá enviar uma resposta rápida que permita ao desenvolvedor saber quando você irá revisar, sugerir outros revisores que possam responder mais rapidamente, ou [forneça alguns comentários amplos iniciais](navigae.md). (Nota: nada disso significa que você deve interromper a codificação mesmo que for para enviar uma resposta como esta &mdash; envie a resposta em uma pausa em seu trabalho.)

**É importante que os revisores gastem tempo suficiente na revisão para que seja certo que seu "LGTM" signifique "este código atende os [nossos padrões](standard.md)."**
No entanto, as respostas individuais ainda devem ser [rápidas](#fast).

## Avaliações Entre Fuso Horários {#tz}

Ao lidar com diferenças de fuso horário, tente responder ao autor enquanto eles têm tempo para responder antes do final de suas horas de trabalho. Se eles ja terminaram o trabalho do dia, então tente certificar-se de que sua revisão foi feita antes deles começarem a trabalhar no dia seguinte.

## LGTM Com Comentários {#lgtm-with-comments}

Para acelerar as revisões de código, existem certas situações em que um revisor deve dar LGTM/Aprovação mesmo que eles também estejam deixando sem solução comentários sobre o CL. Isso é feito quando:

- O revisor está confiante de que o desenvolvedor abordará adequadamente todos os comentários restantes do revisor.

- As alterações restantes são pequenas e não _tem_ que ser feitas pelo desenvolvedor.

O revisor deve especificar qual dessas opções escolheu, se não estiver claro.

Vale a pena considerar o LGTM com comentários especialmente quando o desenvolvedor e revisor estão em fusos horários diferentes e, caso contrário, o desenvolvedor ficaria esperando um dia inteiro apenas para obter "A aprovação por, LGTM."

## CLs Grandes {#large}

Se alguém lhe enviar uma revisão de código tão grande que você não tenha certeza de quando terá tempo para revisá-lo, sua resposta típica deve ser pedir para o desenvolvedor [dividir a CL em várias CLs menores](../developer/small-cls.md) que se baseiam uns nos outros, em vez de uma CL enorme que precisa ser revisado de uma só vez. Isto é geralmente possível e muito útil para os revisores, mesmo que exija trabalho adicional do desenvolvedor.

Se uma CL _não puder_ ser dividida em CLs menores e você não tiver tempo para revisar a coisa toda rapidamente, então pelo menos escreva de volta alguns comentários gerais sobre o design da CL ao desenvolvedor para melhoria. Um dos seus objetivos como um revisor deve ser sempre desbloquear o desenvolvedor ou permitir que ele tome alguma ação adicional rapidamente, sem sacrificar a saúde do código para fazer isso.

## Melhorias na Revisão de Código ao Longo do Tempo {#time}

Se você seguir essas diretrizes e for rigoroso com suas revisões de código, você deve descobrir que todo o processo de revisão de código tende a ser cada vez mais rápido conforme o tempo passa. Os desenvolvedores aprendem o que é necessário para manter o código íntegro e enviam para você CLs que são boas desde o começo, exigindo cada vez menos tempo de revisão. Revisores aprendem a responder rapidamente e não adicionar latência desnecessária ao processo de revisão. Mas **não comprometa os [padrões de revisão de código](standard.md) ou a qualidade para a imaginada melhoria na velocidade** &mdash; Na verdade, isso não vai fazer nada acontecer mais rapidamente, a longo prazo.

## Emergências

Existem também [emergências](../emergencies.md) onde os CLs devem passar por _todo_ processo de revisão muito rapidamente e onde as diretrizes de qualidade seriam diminuídas. No entanto, consulte [O Que é Uma Emergência?](../emergencies.md#o-que-é-uma-emergência-what) para uma descrição de quais situações realmente se qualificam como emergências e quais não.

Próximo: [Como Escrever Comentários de Revisão de Código](comments.md)
