# Emergencies

Às vezes, há CLs de emergência que devem passar por todo processo de revisão de código da forma mais rápida possível.

## O que é uma emergência? {#what}

Uma CL de emergência seria uma **pequena** mudança que: permite que um grande lançamento continue em vez de ter que reverter o código, corrige um bug que afeta significativamente os usuários em produção, lida com uma questão legal urgente, fecha uma grande brecha de segurança, etc.

Em emergências, realmente nos preocupamos com a velocidade do processo de revisão do código e não apenas só com a [velocidade de resposta](reviewer/speed.md). Nesse caso _somente_, o revisor deve se preocupar mais com a velocidade da revisão e a correção do código (ele realmente resolve a emergência?) do que qualquer outra coisa. Além disso (talvez obviamente), quando elas surgem, tais revisões devem ter prioridade sobre todas as outras.

No entanto, depois que a emergência for resolvida, você deve examinar as CLs de emergência novamente e dar uma [análise mais completa](reviewer/looking-for.md).

## O que NÃO é uma emergência? {#not}

Para ser claro, os seguintes casos _não_ são uma emergência:

- Querendo lançar esta semana e não na próxima (a menos que haja algum [prazo fixo](#deadlines) real para o lançamento, como um contrato de parceria).
- O desenvolvedor trabalhou em um recurso por muito tempo e ele realmente deseja que a CL entre no código principal.
- Os revisores estão todos em outro fuso horário onde atualmente é noturno ou eles estão fora do local.
- É o final do dia em uma sexta-feira e seria ótimo conseguir essa CL antes do desenvolvdor sair para o fim de semana.
- Um gerente diz que esta revisão deve ser concluída e a CL verificada hoje por causa de um prazo [suave, (não fixo)](#deadlines).
- Revertendo uma CL que está causando falhas de testes ou quebras de compilação.

E por ai vai.

## O que é um prazo rígido? {#deadlines}

Um prazo rígido é aquele em que **algo desastroso aconteceria** se você perder ele. Por exemplo:

- O envio da sua CL até uma determinada data é necessário para uma obrigação contratual.
- Seu produto falhará completamente no mercado se não for lançado em uma determinada data.
- Alguns fabricantes de hardware só enviam hardware novo uma vez por ano. Se você perder o prazo para enviar o código para eles, o que pode ser desastroso, dependendo que tipo de código você está tentando enviar.

Atrasar um lançamento por uma semana não é desastroso. Perder uma conferência importante pode ser desastroso, mas muitas vezes não é.

A maioria dos prazos são prazos flexíveis, não prazos rígidos. Eles representam um desejo para que um recurso seja feito em um determinado tempo. Eles são importantes, mas você não deveria sacrificar a saúde do código para fazê-los.

Se você tiver um longo ciclo de lançamento (várias semanas), pode ser tentador sacrificar qualidade de revisão de código para obter um recuros antes do próximo ciclo. No entanto, este padrão, se repetido, é uma maneira comum de projetos acumularem dívida técnica. Se os desenvolvedores enviando CLs rotineiramente perto do final do ciclo que "deve entrar" com apenas uma revisão superficial, então a equipe deve modificar seu processo para que grandes mudanças de recursos aconteçam no início do ciclo e ter tempo suficiente para uma boa revisão.
