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
Testes automatizados são fundamentais para um desenvolvimento de qualidade e é obrigação do desenvolvedor escrevê-los