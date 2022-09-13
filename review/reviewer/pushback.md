# Como Lidar com Negativas nas Revisões de Código

Às vezes, um desenvolvedor não aceitará uma revisão de código. Ou eles vão discordar com a sua sugestão ou eles vão reclamar que você está sendo muito rigoroso no geral.

## Quem está certo? {#who_is_right}

Quando desenvolvedores discordarem de sua sugestão, primeiro reserve um momento para considerar se ele estão corretos. Na maioria das vezes, eles estão mais próximos do código do que você e assim eles podem realmente ter uma visão melhor sobre certos aspectos dele. Será que os argumentos deles fazem sentido? Fazem sentido do ponto de vista de saúde do código? Se for assim, deixe-os saber que eles estão certos e deixe a questão de lado.

No entanto, os desenvolvedores nem sempre estão certos. Neste caso, o revisor deve explicar melhor por que eles acreditam que sua sugestão está correta. Uma boa explicação demonstra tanto uma compreensão da resposta do desenvolvedor e informações adicionais sobre por que a mudança está sendo solicitada.

Em particular, quando o revisor acredita que sua sugestão melhorará a saúde do código, eles devem continuar a defender a mudança, se acreditarem que o a melhoria de qualidade de código resultante justifica o trabalho adicional solicitado. **Melhorar a saúde do código tende a acontecer em pequenas etapas.**

Às vezes, são necessárias algumas rodadas para explicar uma sugestão antes que ela realmente seja entendida. Apenas certifique-se de ser sempre [educado](comments.md#courtesy) e deixe o desenvolvedor saber que você _ouve_ o que ele está dizendo, você só não _concorda_.

## Desagradando os Desenvolvedores {#upsetting_developers}

Às vezes, os revisores acreditam que o desenvolvedor ficará chateado se o revisor insiste em uma melhoria. Às vezes os desenvolvedores ficam chateados, mas é rapidamente e eles ficam muito agradecidos depois que você os ajudou a melhorar a qualidade do seu código. Normalmente, se você for [educado](comments.md#courtesy) em seus comentários, os desenvolvedores não ficam nem um pouco chateados e a preocupação é apenas na mente do revisor. As pertubações são geralmente mais sobre [a forma como os comentários são escritos](comments.md#courtesy) do que os insistentes comentários do revisor sobre a qualidade do código.

## Limpando Mais Tarde {#later}

Um motivo comum para não aceitar os feedbacks, é que os desenvolvedores (compreensivelmente) querem ter coisas feitas. Eles não querem passar por outra rodada de revisão apenas para a CL ser aceita. Então eles dizem que vão limpar algo em uma CL posterior e pedem para você dar LGTM _neste_ CL agora. Alguns desenvolvedores são muito bons nisso e vão imediatamente escrever uma CL de auxiliar para corrijir esse problema. No entanto, a experiência mostra que quanto mais tempo passa depois que um desenvolvedor escreveu a CL original, é menos provável que essa limpeza aconteça. Na verdade, geralmente, a menos que o desenvolvedor faça a limpeza _imediatamente_ após a CL atual entrar, isso nunca vai acontecer. Isso não é porque os desenvolvedores são irresponsáveis, mas porque eles têm muito trabalho a fazer e a limpeza se perde ou é esquecida na pressa de outros trabalhos. Assim, geralmente é melhor insistir que o desenvolvedor limpe sua CL _agora_, antes que o código entre na base de código e esteja "pronto." Deixar as pessoas "limparem as coisas mais tarde" é uma maneira comum de degenerar as bases de código.

Se uma CL introduzir uma nova complexidade, ela deve ser limpa antes do envio, a menos que seja uma [emergência](../emergencies.md). Se o CL expõe problemas no ambiente e eles não podem ser resolvidos agora, o desenvolvedor deve registrar um bug para a limpeza e atribuir para si mesmo para que não se perca. Eles, opcionalmente, podem escrever um comentário TODO no código que faz referência ao bug encontrado.

## Reclamações Gerais Sobre Rigorosidade {#strictness}

Se você anteriormente tinha revisões de código bastante negligentes e passa a ser rigoroso em suas reviews, alguns desenvolvedores vão reclamar bastante. Melhorando a [velocidade](speed.md) de suas revisões de código faz com que geralmente essas reclamações desapareçam.

Às vezes pode levar meses para que essas queixas desapareçam, mas eventualmente os desenvolvedores tendem a ver o valor de revisões de código estritas à medida que veem o grande código que eles ajudaram a gerar. Às vezes, os manifestantes mais barulhentos até se tornam seus adeptos mais fortes quando acontece algo que os faz realmente ver o valor da rigorosidade que você está adicionando.

## Resolvendo Conflitos {#conflicts}

Se você está seguindo todos os itens acima, mas ainda encontra um conflito entre você e um desenvolvedor que não pode ser resolvido, consulte [O Padrão de Revisão de Código](standard.md) para diretrizes e princípios que podem ajudar a resolver o conflito.
