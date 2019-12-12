# Test-Driven Development: Teste e Design no Mundo Real 
###### Livro por Mauricio Aniche

### Resumo 

TDD é uma das práticas de desenvolvimento de software sugeridas por diversas metodologias ágeis, como XP. **O TDD sugere que o desenvolvedor escreva o teste antes da implementação.**

// reescrever 
Escrever testes de unidade forçará o desenvolvedor a escrever um código de melhor qualidade pois, como veremos ao longo do livro, para escrever bons testes de unidade, o desenvolvedor é obrigado a fazer um bom uso de orientação a objetos. 

Mesmo que você já pratique TDD, tenho certeza de que encontrará discussões interessantes sobre como a prática dá feedback sobre problemas de acoplamento e coesão, bem como técnicas para escrever testes melhores e mais fáceis de serem mantidos. 

Todo capítulo possui sua parte prática e parte teórica. 

### Capítulo 1: Introdução

Nos EUA estimam que bugs de software lhes custam aproximadamente 60 bilhões de dólares por ano. 

Por que não testamos? 
Não testamos, porque testar sai caro. 

Uma maneira para conseguir testar o sistema todo de maneira constante e contínua a um preço justo é automatizando os testes.

Um ponto que é sempre levantado em qualquer discussão sobre testes manuais versus testes automatizados é produtividade. 

A resposta para essa pergunta é: o que é produtividade?

Ele escreve um pouco, roda o programa, o programa falha. Nesse momento, o desenvolvimento entende o problema, corrige-o, e em seguida executa novamente o mesmo teste.

### Capítulo 2: Testes de unidade

Um teste de unidade não se preocupa com todo o sitema. 

Geralmente, em sistemas orientados a objetos, essa unidade é a classe. 

O primeiro teste de unidade.
Idealmente, a cada alteração feita, todo sistema deve ser testado por inteiro novamente.

Ou seja, de forma generalizada, o desenvolvedor primeiro pensa em um cenário (dois produtos comprados), depois executa uma ação (vai ao carrinho de compras) e, por último, valida a saída (vê a quantidade de itens e o valor total do carrinho). 

Veja que esse código contém, de forma automatizada, boa parte do que foi descrito em relação ao teste manual: ele monta um cenário (um carrinho de compras com 3 produtos), executa uma ação (invoca o método) e valida a saída (imprime o maior e o menor produto). 

Para melhorar esse código, agora só introduzindo um framework de teste automatizado.

A única parte que ainda não é feita 100% pela máquina é a terceira parte do teste: a validação. 

> Se algum dia um outro desenvolvedor altera esse código, ele poderá executar a bateria de testes automatizados existente e, descobrir se a sua alteração fez alguma funcionalidade que já funcionava anteriormente parar de funcionar.
**Isso é teste de regressão.**

Por que não criar um software que automatize o seu próprio ciclo de trabalho?
Testes automatizados são fundamentais para um desenvolvimento de qualidade e é obrigação do desenvolvedor escrevê-los.

### Capítulo 3: Introdução ao Test-Driven Development

Uma pergunta interessante é: será que é possível inverter, ou seja, testar primeiro e depois implementar? E mais importante, faz algum sentido?

Conhecendo o problema dos numerais romanos, é possível levantar os diferentes cenários que precisam ser aceitos pelo algoritmo: um símbolo, dois símbolos iguais, três símbolos iguais, dois símbolos diferentes do maior para o menos, quatro símbolos dois a dois e assim por diante. 

Para fazê-lo passar, introduziremos ainda uma segunda regra: **o código escrito deve ser sempre o mais simples possível**.

O ciclo repetido até aqui foi: 

* Escrevemos um teste de unidade para uma nova funcionalidade;
* Vimos o teste falhar;
* Implementamos o código o mais simples para resolver o problema;
* Vimos o teste passar;
* Melhoramos (refatoramos) nosso código quando necessário. 

Esse ciclo também é conhecido como ciclo **vermelho-verde-refatora** (ou red-green-refactor).

Quais as vantagens no TDD no processo de desenvolvimento? 

* Foco no teste e não na implementação; 
* Código nasce testado;
* Simplicidade;
* Melhor reflexão sobre o design da classe;

Há uma diferença crucial na quantidade de *feedback* que um programador praticamente de TDD recebe e um não praticante. 

Ao receber o feedback desde cedo, o programador pode melhorar o código e corrigir problemas a um custo menor do que o programador que recebeu a mesma mensagem muito tempo depois.

**No fim TDD apenas maximiza a quantidade de feedback sobre o código que está sendo produzido, fazendo o programador perceber os problemas antecipadamente e, por consequência, diminuindo os custos de manutenção e melhorando o código**

TDD ficou bastante conhecido após a publicação do livro TDD by example, do Kent Beck, em 2002. 

> As pessoas sempre falavam para ele conseguir separar o que o programa deve fazer da sua implementação final, mas ele não sabia como fazer, até aquele momento em que resolveu escrever o teste antes.

*E quanto à repetição de código dentro do próprio teste? É possível melhorar a qualidade de código do próprio teste?*

### Capítulo 4: A simplicidade e baby steps

Hora de fazer o teste passar mas lembre-se de que a ideia é fazer o teste passar da maneira **mais simples possível**.

A ideia de sempre tomar o passo mais simples que resolva o problema naquele momento (e faça o teste passar) é conhecido pelos praticantes do TDD como **baby steps**.

Generalizando o ponto levantado: o desenvolvedor, em vez de partir para uma solução mais abstrata que resolveria o problema de forma genérica, prefere ficar postergando a implementação final, com a desculpa de estar praticando passos de bebê. 

O desenvolvedor deve buscar pela **solução mais simples** e não pela **modificação mais simples**. 

Em nosso exemplo, veja que a solução mais simples acabou sendo o uso de `if's`. Sabemos que todo condicional faz o código ser mais difíciil de ser mantido e de ser testado. Sabemos que essa não é a melhor solução para o problema; o uso de polimorfismo seria mais adequado. 

**A mudança mais simples para resolver um problema não é ncessariamente a solução mais simples para resolvê-lo.**

Todo desenvolvedor sabe que deve refatorar qualquer duplicidade de código no momento que a encontrar. 

Lembre-se de que o objetivo do desenvolvedor não é praticar TDD, mas sim entregar código de qualidade. TDD e passos de bebê estão lá para ajudar mas não são regras de ouro. 

##### Uncle Bob e os passos de refatoração do TDD

##### Vantagem de fazer o teste passar rápido

Uma das vantagens de fazer o teste passar de maneira simples e rápida é "testar o teste". Seu teste é código, e ele pode ter bugs também. 

Uma maneira de testá-lo é garantir que ele falhe quando precise falhar, e passe quando precise passar. 

Parafraseando Jason Gorman, *"se fazer a coisa simples significa fazer o uso de muitos if's ou switchs, muito provavelmente você não entendeu TDD"*. 

### Capítulo 5: TDD e design de classes

##### O problema do carrinho de compras

* Se o carrinho só tiver um item, ele mesmo será o item de maior valor. 
* Se o carrinho tiver muitos itens, o item de maior valor é o que deverá ser retornado.
* Um carrinho sem nenhum item deve retornar zero.

Fazemos o teste passar e como ainda nao há uma repetição de código grande a ser eliminada, então podemos ir para o próximo teste. 

Em que momento mudamos o rumo da implementação? (a não necessidade de um cenário para a classe sob o teste)

Muitos praticantes de TDD afirmam que a prática lhes guia no projeto de classes. 

**A prática do TDD não guia o desenvolvedor para um bom projeto de classes de forma automática; a experiência e conhecimento do desenvolvedor são fundamentais ao criar software orientado a objetos.**

##### Diferenças entre o TDD e testes de maneira tradicional

