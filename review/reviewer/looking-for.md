# O que procurar em uma revisão de código

Note: Always make sure to take into account
[The Standard of Code Review](standard.md) when considering each of these
points.

Nota: Certifique-se de sempre levar em conta [O Padrão de Revisão de Código](standard.md) ao considerar cada um desses pontos.

## Design

A coisa mais importante a ser abordada em uma revisão é o design geral da CL. As interações de vários pedaços de código na CL fazem sentido? Essa mudança pertence à sua base de código ou a uma biblioteca? Ela se integra bem com o resto do seu sistema? Agora é um bom momento para adicionar essa funcionalidade?

## Funcionalidade

Esta CL faz o que o desenvolvedor pretendia? É o que o desenvolvendor planejava para os usuários deste código? Os "usuários" geralmente são os usuários finais (quando são afetados pela mudança) e os desenvolvedores (que terão que "usar" este código no futuro).

Sobretudo, esperamos que os desenvolvedores testem as CLs o suficiente para que funcionem corretamente antes que ela chegue na revisão de código. No entando, como revisor, você ainda deve estar pensando em casos extremos, procurando problemas de simultaneidade, tentando pensar como um usuário e certificando-se de que não há bugs que você veria apenas lendo o código.

Você _pode_ validar a CL, se quiser, no momento em que é mais importante para um revisor analisar o comportamento de uma CL, que é quando ele tem um impacto voltado para o usuário, como em uma **Alteração da interface**. É difícil entender como algumas mudanças afetarão o usuário quando você está apenas lendo o código. Para mudanças como essa, você pode pedir para o desenvolvedor lhe dar uma demonstração da funcionalidade, caso seja muito inconveniente juntar na CL e tentar você mesmo.

Outro momento em que é particularmente importante pensar na funcionalidade durante uma revisão de código, é quando há algum tipo de **programação paralela** acontecendo na CL que teoricamente poderia causar deadlocks ou condições de corrida. Esses tipos de problemas são muito difíceis de detectar apenas executando o código e geralmente precisam de alguém (tanto o desenvolvedor quanto o revisor) para pensar sobre eles cuidadosamente para ter certeza de que esses problemas não continuarão. (Observe que isso é também uma boa razão para não usar modelos de concorrência onde as condições de corrida ou deadlocks são possíveis de acontecer, pode tornar muito complexo fazer revisões de código ou entender o código.)

## Complexidade

A CL é mais complexa do que deveria ser? Verifique isso em todos os níveis da CL, as linhas individuais são muito complexas? As funções são muito complexas? As classes são muito complexas? "Muito complexo" geralmente significa **"não pode ser entendido rapidamente por leitores de código."** Também pode significar **"os desenvolvedores provavelmente introduzirão bugs quando tentarem modificar este código."**

Um tipo específico de complexidade é a **engenharia excessiva**, em que os desenvolvedores tornaram o código mais genérico do que precisaria ser, ou adicionaram funcionalidades que atualmente não são necessárias pelo sistema. Os revisores devem estar especialmente atentos com a engenharia excessiva. Incentive os desenvolvedores a resolver o problema que eles conhecem e que precisa ser resolvido _agora_, não o problema que o desenvolvedor especula que _poderia_ ser resolvido no futuro. O problema do futuro deve ser resolvido uma vez que ele chega e você pode ver sua forma e requisitos reais no universo.

## Testes

Solicite testes de unidade, testes de integração e testes ponta a ponta conforme apropriado para a mudança. Em geral, os testes devem ser adicionados na mesma CL que o código de produção, a menos que a CL esteja lidando com uma [emergência](../emergencies.md).

Certifique-se de que os testes na CL estejam corretos, sensatos e úteis. Testes fazem testes, eles não se testam, e raramente escrevemos testes para nossos testes, um humano deve garantir que os testes são válidos.

Os testes realmente falham quando o código está quebrado? Se o código mudar abaixo deles, eles começarão a produzir falsos positivos? Cada teste faz afirmações simples e úteis? Os testes estão separados adequadamente entre métodos de teste diferentes?

Lembre-se de que os testes também são códigos que precisam ser mantidos. Não aceite complexidade em testes apenas porque eles não fazem parte do binário principal.

## Nomenclatura

O desenvolvedor escolheu bons nomes para tudo? Um bom nome é longo o suficiente para comunicar totalmente o que o item é ou faz, sem ser tão longo que torna-se difícil de ler.

## Comentários

O desenvolvedor escreveu comentários claros e entendíveis? São todos os comentários realmente necessários? Normalmente os comentários são úteis quando **explicam por que** algum código existe e não devem estar explicando _o que_ algum código está fazendo. Se o código não for claro o suficiente para se explicar, então o código deve ser feito mais simples. Existem algumas exceções (expressões regulares e algorítimos complexos, por exemplo, muitas vezes se beneficiam muito de comentários que explicam o que estão fazendo), mas principalmente os comentários são para informações que o próprio código não pode possivelmente conter, como o raciocínio por trás de uma decisão.

Também pode ser útil olhar os comentários que existiam antes desta CL. Pode ser que haja um TO-DO que pode ser removido agora, um comentário desaconselhando essa alteração, etc.

Observe que os comentários são diferentes da _documentação_ de classes, módulos ou funções, que devem, em vez disso, expressar o propósito de um pedaço de código, como ele deve ser usado e como ele se comporta quando usado.

## Estilo

Temos [guias de estilo](http://google.github.io/styleguide/) no Google para todas as nossas principais linguagens e para a maioria das linguagens secundárias. Certifique-se que a CL segue os guias de estilo apropriados.

Se você quiser melhorar algum ponto de estilo que não está no guia de estilo, prefixe seu comentário com "Nit:" para que o desenvolvedor saiba que é um detalhe que você achou que melhoraria o código, mas não é obrigatório. Não impeça as CLs de serem integradas ao código com base apenas em preferências pessoais de estilo.

O autor da CL não deve incluir grandes mudanças de estilo combinadas com outras mudanças. Dificulta ver o que está sendo alterado na CL, torna as merges e as reversões mais complexas, além de causar outros problemas. Por exemplo, se o autor deseja formatar o arquivo inteiro, peça que ele envie apenas a formatação como uma CL e, em seguida, enviar outra CL com suas alterações funcionais.

## Consistência

E se o código existente for inconsistente com o guia de estilo? Por nossos [princípios de revisão de código](standard.md#principles), o guia de estilo é a autoridade absoluta: se algo é exigido pelo guia de estilo, a CL deve seguir as orientações.

Em alguns casos, o guia de estilo faz recomendações em vez de declarar requisitos. Nesses casos, é de próprio julgamento se o novo código deve ser consistente com as recomendações ou pelo menos próximo à elas. A tendência é seguir o guia de estilo, a menos que a inconsistência local seja muito confusa.

Se nenhuma outra regra se aplicar, o autor deve manter a consistência com o código existente.

De qualquer forma, incentive o autor a registrar um bug e adicionar um TO-DO para limpeza do código existente.

## Documentação

Se uma CL alterar a forma como os usuários criam, testam, interagem ou lançam o código, verifique se ele também atualiza a documentação associada, incluindo READMEs, páginas g3doc e qualquer documentos gerados de referência. Se a CL excluir ou descontinuar o código, considere que a documentação também deva ser excluída.

## Cada Linha {#every-line}

No caso geral, veja _toda_ linha de código que lhe foi atribuída para revisão. Algumas coisas como arquivos de dados, código gerado ou grandes estruturas de dados você pode apenas escanear por cima, mas não revise por cima uma classe, funções ou blocos de códigos escrito por humanos assumindo que isso está bom. Obviamente, alguns códigos merecem uma análise mais cuidadosa do que outros códigos &mdash; Isso é um julgamento que você tem que fazer &mdash; Porém você deve pelo menos ter certeza de que você _entende_ o que todo o código está fazendo.

Se for muito difícil para você ler o código e isso atrasar a revisão, então você deve informar ao desenvolvedor sobre isso e que espera que ele esclareça antes da sua revisão. No Google, contratamos grandes engenheiros de software, e você é um deles. Se você não consegue entender o código, é muito provável que outros desenvolvedores também não. Então você também está ajudando futuros desenvolvedores a entender esse código, quando pede ao desenvolvedor para esclarecê-lo.

Se você entende o código, mas não se sente qualificado para fazer alguma parte da revisão, [certifique-se de que há um revisor](#every-line-exceptions) na CL que é qualificado, especialmente para questões complexas como privacidade, segurança, simultaneidade, acessibilidade, internacionalização, etc.

### Exceções {#every-line-exceptions}

E se não fizer sentido para você revisar todas as linhas? Por exemplo, você pode ser um dos vários revisores em uma CL e pode ser pedido:

- Para revisar apenas determinados arquivos que fazem parte de uma alteração maior.
- Rever apenas alguns aspectos da CL, como o design de alto nível, implicações de privacidade ou segurança, etc.

Nesses casos, anote em um comentário quais partes você revisou. Prefira dar [LGTM com comentários](speed.md#lgtm-with-comments)

Se, em vez disso, você deseja conceder LGTM após confirmar que outros revisores revisaram as outras partes da CL, cite isso explicitamente em um comentário para alinhar as expectativas. Procure [responder rapidamente](speed.md#responses) assim que a CL tiver atigindo o estado desejado.

## Contexto

Muitas vezes é útil olhar para a CL em um contexto amplo. Normalmente a ferramenta de revisão de código mostrará apenas algumas linhas de código em torno das partes que estão sendo alteradas. Às vezes você tem que olhar o arquivo inteiro para ter certeza de que as mudanças realmente fazem sentido. Por exemplo, você pode ver apenas quatro novas linhas sendo adicionadas, mas quando você olha para o arquivo inteiro, você vê que essas quatro linhas são em um método de 50 linhas que agora realmente precisa ser dividido em métodos menores.

Também é útil pensar na CL no contexto do sistema como um todo.
Esta CL está melhorando a integridade do código do sistema ou está tornando todo o sistema mais complexo, menos testado, etc? **Não aceite CLs que degradem o código e a saúde do sistema.** A maioria dos sistemas se tornam complexos por meio de muitas pequenas mudanças que se somam, por isso é importante evitar até mesmo pequenas complexidades em novas mudanças.

## Coisas boas {#good-things}

Se você vir algo legal na CL, diga ao desenvolvedor, especialmente quando ele abordou um de seus comentários de uma maneira excelente. As revisões de código geralmente se concentram apenas em erros, mas eles devem oferecer encorajamento e apreço por boas práticas também. Às vezes é ainda mais valioso em termos de orientação, dizer a um desenvolvedor o que eles fizeram de certo do que dizer a eles o que eles fizeram de errado.

## Resumo

Ao fazer uma revisão de código, você deve certificar-se de que:

- O código é bem projetado.
- A funcionalidade é boa para os usuários do código.
- Quaisquer alterações na interface do usuário são sensatas e com boa aparência.
- Qualquer programação paralela é feita com segurança.
- O código não é mais complexo do que precisa ser.
- O desenvolvedor não está implementando coisas que eles _podem_ precisar no futuro, mas que eles não precisam agora.
- O código tem testes de unidade apropriados.
- Os testes são bem projetados.
- O desenvolvedor usou nomes claros para tudo.
- Os comentários são claros e úteis, e principalmente explicam _por que_ em vez de _o que_.
- O código está devidamente documentado (geralmente em g3doc).
- O código está em conformidade com nossos guias de estilo.

Certifique-se de revisar **cada linha** de código que você foi solicitado a revisar, olhar o **contexto**, verificar se você está **melhorando a integridade do código** e elogie desenvolvedores em **coisas boas** que eles fazem.

Próximo: [Navegar em uma CL em Revisão](navigate.md)
