---
title: Teste de Unidade
tags: []
---

# Teste de Unidade

*  Teste de unidade dá feedback ao seu design.
*  O Feedback deve chegar o quanto antes.
*  TDD é uma boa opcao para tornar mais facil e rapido o retorno do feedback.
*  Teste de unidade sao atividades de construcao.
*  Cobertura de testes prove confianca.
*  Refatoracao sem cobertura pode ser uma ventura.
*  Teste tambem é codigo e deve ser limpo.

## TDD

### As tres leis do TDD

*  Primeira lei

    Nao se deve escrever o código de producao ate criar um teste de unidade de falhas.

*  Segunda lei

    Nao se deve escrever mais de um teste de unidade do que o necessario para falhar e nao compilar é falhar.

* Terceira lei

    Nao se deve escrever mais codigo de producao do que o necessario para aplicar o teste de falha atual.

## Teste limpos

### F.I.R.S.T

Teste limpos seguem outras cinco regras que formam o acronimo em ingles acima (Fast, Idependent, Repeatable, Self-validating, Timely):

* Rapidez

    Os testes devem ser rapidos. Devem executar com rapidez. Quando os testes rodam devagar, voce nao desejará executa-lo com frequencia. E consequentemente, nao encontratara problemas cedo o bastante para conserta-los facilmente.

* Independencia

    Os teste nao devem depender uns dos outros. Um teste nao deve configurar as condicoes para o proximo. Voce deve ser capaz de executar cada teste de forma independente e na ordem qe desejar.

* Repetividade

    Deve-se poder repetir os testes em qualquer ambiente. Caso seus testes nao possam ser repetidos em qualquer ambiente, entao voce sempre terá uma desculpa para o motivodas falhas
    
* Autovalidacao

    Os testes devem ter uma saida booleana. Se os testesnao possuirem  autovalidacao, entao uma falha pode se tornar subjetiva, e executar os testes pode exigir uma longa validacao manual.
    
* Pontualidade

    Os testes precisam ser escritos m tempo habil. Devem-se criar os testes de unidade imediatamente antes do codigo de producao no qual serao aplicados. Se cria-los depois, o teste de codigo de producao poderá ficar mais dificil.
