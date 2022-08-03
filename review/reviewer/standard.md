# O Padrão de Revisão de Código

O objetivo principal da revisão de código é certificar-se de que a saúde da base de código do Google continue melhorando ao longo do tempo. Todas as ferramentas e processos de revisão de código são projetados para este fim.

Para conseguir isso, uma série de trocas são feitas para manter o equilíbrio.

Primeiro, os desenvolvedores devem ser capazes de _progredir_ em suas tarefas. Se você nunca enviar uma melhoria para a base de código, então a base de código nunca melhora. Também, se um revisor dificulta muito a entrada de _qualquer_ alteração, os desenvolvedores são desincentivados a fazer melhorias no futuro.

Por outro lado, é dever do revisor certificar-se de que cada CL, é de tal qualidade, que a saúde geral do código de sua base de código não diminua com o passar do tempo. Isso pode ser complicado, porque muitas vezes as bases de código se degradam através de pequenas diminuições na saúde do código ao longo do tempo, especialmente quando uma equipe está sob restrições de tempo significativas e eles sentem que têm que tomar atalhos para atingir seus objetivos.

Além disso, um revisor tem propriedade e responsabilidade sobre o código que está revendo. Eles querem garantir que a base de código permaneça consistente, sustentável e todas as outras coisas mencionadas em ["O Que Procurar em uma Revisão de Código."](looking-for.md)

Assim, assumimos a seguinte regra como padrão nas revisões de código:

**Em geral, os revisores devem favorecer a aprovação de uma CL quando estiver em um estado em que definitivamente melhora a saúde geral do código do sistema sendo trabalhado, mesmo que a CL não seja perfeita.**

Esse é o princípio sênior entre todas as diretrizes de revisão de código.

Há limitações para isso, é claro. Por exemplo, se uma CL adiciona um recurso que o revisor não quer em seu sistema, então o revisor deve certamente rejeitar a aprovação, mesmo que o código seja bem projetado.

Um ponto-chave aqui é que não existe código "perfeito" code&mdash; Existe apenas um _melhor_ código. Os revisores não devem exigir que o autor aperfeiçoe cada pequena parte de uma CL antes de conceder a aprovação. Em vez disso, o revisor deve equilibrar a necessidade de avançar em relação à importância das mudanças que eles estão sugerindo. Em vez de buscar a perfeição, o que um revisor deve buscar é a _melhoria continua_. Uma CL que, como um todo, melhora a manutenibilidade, legibilidade e compreensão do sistema, não deve ser atrasada por dias ou semanas porque não é "perfeito".

Os revisores devem _sempre_ sentir-se à vontade para deixar comentários expressando que algo poderia ser melhor, mas se não for muito importante, prefixe-o com algo como "Nit: " (algo que não está perfeito, porém aceitável) para deixar o autor saber que é apenas um ponto de polimento que ele poderiam ignorar.

Nota: Nada neste documento justifica a aprovação de CLs que definitivamente _pioram_ a saúde geral do código do sistema. A única vez que você faria isso estaria em uma [emergência](../emergencies.md).

## Mentoria

Code review can have an important function of teaching developers something new
about a language, a framework, or general software design principles. It's
always fine to leave comments that help a developer learn something new. Sharing
knowledge is part of improving the code health of a system over time. Just keep
in mind that if your comment is purely educational, but not critical to meeting
the standards described in this document, prefix it with "Nit: " or otherwise
indicate that it's not mandatory for the author to resolve it in this CL.

A revisão de código pode ter uma função importante de ensinar aos desenvolvedores algo novo sobre uma linguagem, uma estrutura ou princípios gerais de design de software. É sempre bom deixar comentários que ajudem um desenvolvedor a aprender algo novo. Compartilhar conhecimento faz parte da melhoria da saúde do código de um sistema ao longo do tempo. Apenas guarde em mente que, se seu comentário for puramente educacional, mas não crítico para atender os padrões descritos neste documento, prefixe-o com "Nit: " ou de outra forma indicando que não é obrigatório para o autor resolvê-lo nesta CL.

## Princípios {#principles}

- Fatos e dados técnicos anulam opiniões e preferências pessoais.

- Em questões de estilo, o [guia de estilo](http://google.github.io/styleguide/) é a autoridade absoluta. Qualquer ponto puramente de estilo (espaço em branco, etc.) que não está no guia de estilo, é uma preferência pessoal. O estilo deve ser consistente com o que está lá. Se não houver estilo anterior, aceite o que o autor propõe.

- **Ascpectos de design de software quase nunca são uma questão puramente de estilo ou apenas uma preferência pessoal.** Eles são baseados em princípios básicos e devem ser mantidos por esses príncipios e não, simplesmente, por opinião pessoal. Às vezes existem lá algumas outras opiniões válidas. Se o autor puder demonstrar (seja por meio de dados ou baseado em sólidos princípios de engenharia) que várias abordagens são igualmente válidas, então o revisor deve aceitar a preferência do autor. Caso contrário, a escolha é ditada pelos princípios dos padrões de design de software.

- Se nenhuma outra regra se aplicar, o revisor pode solicitar ao autor que seja consistente com o que está na base de código atual, desde que isso não piore a saúde geral do código do sistema.

## Resolvendo Conflitos {#conflicts}

Durante qualquer conflito em uma revisão de código, o primeiro passo deve ser sempre para o desenvolvedor e o revisor tentarem chegarem a um consenso, com base no conteúdo deste documento e dos demais documentos [O Guia do Autor da CL](../developer/index.md) e este [Guia do revisor](index.md).

Quando chegar a um consenso é muito complicado, isto pode ser resolvido em um encontro presencial ou uma videoconferência entre o revisor e o autor, em vez de ficar tentando resolver o conflito por meio de comentários de revisão de código. (Se vocẽ fizer isso, porém, certifique-se de registrar os resultados da discussão como um comentário sobre o CL, para futuros leitores.)

Se isso não resolver a situação, a maneira mais comum de resolvê-la seria escalar ela. Muitas vezes o caminho de escalonamento é para uma discussão mais ampla da equipe, tendo um líder técnico pesando, perguntando a opinião de um mantenedor do código, ou pedindo ajuda a um Engenheiro Técnico de fora. **Não deixe um CL parado porque o autor e o revisor não podem vir a um acordo.**

Próximo: [O que procurar em uma revisão de código](looking-for.md)
