# Navegando em uma CL em revisão

## Resumo

Agora que você sabe [o que procurar](looking-for.md), qual é a maneira mais eficiente de gerenciar uma revisão que está espalhada por vários arquivos?

1.  A mudança faz sentido? Tem uma boa [descrição](../developer/cl-descriptions.md)?
2.  Veja primeiro a parte mais importante da mudança. Em geral, é bem projetada?
3.  Observe o restante da Lista de Mudanças em uma sequênia apropriada.

## Passo Um: Ter uma visão ampla da mudança {#step_one}

Veja a [descrição da Lista de Mudanças](../developer/cl-descriptions.md) e o que a Lista de Mudanças faz em geral. Essa mudança ainda faz sentido? Se essa mudança não deveria ter acontecido em primeiro lugar, por favor responda imediatamente com uma explicação com o porquê a mudança não deveria estar acontecendo. Quando você rejeita uma mudança como essa, também é uma boa ideia sugerir ao desenvolvedor o que ele deveria ter feito em vez disso.

Por exemplo, você pode dizer "Parece que você se esforçou para fazer isso, obrigado! No entanto, estamos indo na direção de remover o sistema FooWidget que você está modificando aqui e, portanto, não queremos fazer novas modificações para isso agora. Que tal você refatorar nossa nova classe BarWidget?"

Observe que o revisor não apenas rejeitou a Lista de Mudanças atual e forneceu uma sugestão alternativa, mas ele fez isso _cordialmente_. Esse tipo de cortesia é importante porque queremos mostrar que nos respeitamos como desenvolvedores, mesmo quando discordamos.

Se você receber mais do que algumas Listas de Mudanças que representam alterações que você não faria, você deve considerar retrabalhar o processo de desenvolvimento de sua equipe ou o processo para contribuidores externos para que haja mais comunicação antes das CLs serem escritas. É melhor dizer "não" às pessoas antes que elas tenham feito muito trabalho que agora tem de ser jogado fora ou drasticamente reescrito.

## Passo Dois: Examine as principais partes da CL {#step_two}

Encontre o arquivo ou os arquivos que são as partes "principais" desta CL. Muitas vezes, há um arquivo que tem o maior número de alterações lógicas, e é a maior parte da CL. Olhe para essas partes principais primeiro. Isso ajuda a contextualizar todas as partes menores da CL e geralmente acelera a revisão do código. Se a CL é muito grande para você descobrir quais partes são as partes principais, pergunte ao desenvolvedor o que você deve olhar primeiro, ou peça para ele [dividir a CL em várias CLs](../developer/small-cls.md).

Se você encontrar alguns problemas de design importantes com esta parte da CL, você deve enviar esses comentários imediatamente, mesmo que você não tenha tempo para revisar o restante da CL no momento. Na verdade, revisar o resto da CL pode ser um desperdício de tempo, porque se os problemas de design são significativos o suficiente, muitos dos outros códigos sob revisão irão desaparecer e não serão importantes.

Existem dois motivo principais que tornam importante enviar comentários do design imediatamente:

- Os desenvolvedores geralmente enviam uma CL e iniciam imediatamente um novo trabalho com base nessa CL enquanto aguardam a revisão. Se houver grandes problemas de design na CL que você está revisando, eles também terão retrabalho em sua CL posterior. Você deve alertar antes que eles façam muito trabalho extra em cima do design problemático.

- Grandes mudanças de design levam mais tempo para serem feitas do que pequenas mudanças. Quase todos os desenvolvedores têm prazos, para cumprir esses prazos e ainda ter código de qualidade na base de código, o desenvolvedor precisa iniciar qualquer grande retrabalho na CL o mais rápido possível.

## Passo Três: examine o restante da CL em uma sequência apropriada {#step_three}

Depois de confirmar que não há grandes problemas de design com a CL como um todo, tente descobrir uma sequência lógica para examinar os arquivos, enquanto isso, certifique-se de não deixar de revisar nenhum arquivo. Normalmente, depois de examinar os arquivos principais, é mais simples passar por cada arquivo na ordem em que a ferramenta de revisão de código os apresenta a você. Às vezes também é útil ler os testes primeiro antes de ler o código principal, porque assim você tem uma ideia do que a mudança deveria estar fazendo.

Próximo: [Velocidade das Revisões de Códio](speed.md)
