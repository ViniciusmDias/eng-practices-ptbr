# Guia de Revisão de Código do Desenvolvedor

## Introdução {#intro}

Uma revisão de código é um processo em que alguém que não seja(m) o(s) autor(es) de um pedaço de código, examina aquele código.

No Google, usamos a revisão de código para manter a qualidade do nosso código e de produtos.

Esta documentação é a descrição canônica de processos e políticas de revisão de código do Google.

Esta página é uma visão geral do nosso processo de revisão de código. Existem outros dois grandes documentos que fazem parte deste guia:

- **[Como Fazer Uma Revisão de Código](review/index.md)**: Um guia detalhado para revisores de código.
- **[O Guia do Autor da CL](developer/index.md)**: Um guia detalhado para desenvolvedores cujos CLs estão passando por revisão.

## O Que Os Revisores De Código Procuram? {#look_for}

Revisores de código deveriam observar:

- **Style**: Does the code follow our
  [style guides](http://google.github.io/styleguide/)?
- **Documentation**: Did the developer also update relevant documentation?

- **Design**: O código é bem projetado e apropriado para o seu sistema?
- **Funcionalidade**: O código se comporta como o autor previa? É o melhor comportamento para os seus usuários?
- **Complexidade**: O código poderia ser simplificado? Outro desenvolvedor seria capaz de entender e usar facilmente este código quando se deparar com ele no futuro?
- **Testes**: O código possui testes automatizados corretos e bem elaborados?
- **Nomenclatura**: O desenvolvedor escolheu nomes claros para variáveis, classes, métodos, etc?
- **Comentários**: Os comentários são claros e úteis?
- **Estilo**: O código segue nosso [guia de estilo](http://google.github.io/styleguide/)?
- **Documentação**: O desenvolvedor também atualizou a documentação relevante?

Consulte **[Como fazer uma revisão de código](reviewer/index.md)** para mais informações.

### Como escolher os melhores revisores {#best_reviewers}

No geral, você deseja encontrar os _melhores_ revisores que puder e que sejam capazes de responder à sua revisão dentro de um período de tempo razoável.

O melhor revisor é a pessoa que será capaz de lhe dar a revisão mais completa para o pedaço de código que você está escrevendo. Isso geralmente significa que o(s) proprietário(s) do código, podem ou não serem as pessoas as pessoas proprietárias do arquivo. Às vezes, isso significa pedir a diferentes pessoas que revisem diferentes partes do CL.

Se você encontrar um revisor ideal, mas ele não está disponível, você deve pelo menos marcar ele em suas alterações.

### Avaliações pessoalmente (e Programção em Pares) {#in_person}

Se você programou um código em par com alguém qualificado para fazer uma boa revisão nesse código, então esse código é considerado revisado.

Você também pode fazer revisões de código pessoalmente, onde o revisor faz perguntas e o desenvolvedor da mudança fala apenas quando for perguntado.

## Veja também {#seealso}

- [Como Fazer uma Revisão de Código](reviewer/index.md): Um guia detalhado para revisores de código.

- [O Guia do Autor da CL](developer/index.md): Um guia detalhado para desenvolvedores cujos CLs estão passando por revisão.
