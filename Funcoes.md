---
title: Funcoes
tags: []
---

# Funcoes

*  Funcoes devem ser **pequenas** (<=20 linhas).
*  Funcoes deve fazer **apenas uma coisa**.
*  Devem ter nomes descritivos do que fazem.
*  Somente um nivel de abstracao por funcao.
*  Funcoes devem ter poucos parametros.
*  Regra decrescente: Ler o codigo de cima para baixo
*  os blocos if, else, while e outros devem ter apenas uma linha. Possivelmente uma funcao.
*  Nivel de identacao de uma funcao devem ser no maximo um ou dois.
*  Extraia os blocos try/catch. Tratamento de erro é uma coisa só.

** Codigo Ruim: **

``` java
   public double calculaPremio(List<Integer> numerosApostados, double premioTotal)
   {

      //Valida aposta
      
      List<Integer> numerosValidos = new ArrayList<>();
      for (Integer apostado : numerosApostados)
      {
         if (apostado < 1 || apostado > 60)
         {
            return 0.0; // inválido
         }
         if (numerosValidos.contains(apostado))
         {
            return 0.0; // repetido
         }
         numerosValidos.add(apostado);
      }

      //Calcula acertos
      
      if (numerosValidos.size() >= 6 && numerosValidos.size() <= 15)
      {
         List<Integer> numerosSorteados = new ArrayList<>();
         int numeroSorteado;
         while (numerosSorteados.size() < 6)
         {
            numeroSorteado = new Random().nextInt(59) + 1;
            if (!numerosSorteados.contains(numeroSorteado))
            {
               numerosSorteados.add(numeroSorteado);
            }
         }

         int acertos = 0;
         for (Integer apostado : numerosApostados)
         {
            if (numerosSorteados.contains(apostado))
            {
               acertos++;
            }
         }

         //Calcula o premio
         
         if (acertos == 6)
         {
            return premioTotal; // Sena = 100%
         }
         else if (acertos == 5)
         {
            return premioTotal * 0.2; // Quina = 20%
         }
         else if (acertos == 4)
         {
            return premioTotal * 0.05; // Quadra = 5%
         }
      }
      return 0.0;
   }
```

** Codigo Bom: **

``` java
    public double calculaPremio(List<Integer> apostados, List<Integer> sorteados, double premioTotal) {
        if (!isApostaValida(apostados)) {
            throw new IllegalArgumentException("Aposta inválida:" + apostados);
        }
        long acertos = calculaAcertos(apostados, sorteados);
        if (acertos == 6) {
            return premioTotal; // Sena = 100%
        } else if (acertos == 5) {
            return premioTotal * 0.2; // Quina = 20%
        } else if (acertos == 4) {
            return premioTotal * 0.05; // Quadra = 5%
        }
        return 0.0;
    }

    private boolean isApostaValida(List<Integer> numerosApostados) {
        return numerosApostados.size() >= 6 && numerosApostados.size() <= 15 &&
                numerosApostados.stream().distinct().filter(n -> n >= 1 && n <= 60).
                        count() == numerosApostados.size();
    }

    private int calculaAcertos(List<Integer> apostados, List<Integer> sorteados) {
        return (int) apostados.stream().filter(n -> sorteados.contains(n)).count();
    }
```

** Exemplo dos blocos if/else: **

``` java
    if (conta.getTipo() == Conta.CONTA_CORRENTE) 
    {
        return calcularSaldoContaCorrente();
    } 
    else if (conta.getTipo() == Conta.CONTA_POUPANCA) 
    {
        return calcularSaldoContaPoupanca();
    } 
    else if (conta.getTipo() == Conta.CONTA_BENEFICIARIO) 
    {
        return calcularSaldoContaBeneficiario();
    }
```

** Exemplo de extracao de try/catch: **

``` java
    public void delete(Cliente cliente)
    {
        try
        {
            deletaClienteDoBancoDeDados(cliente);
        }
        catch(Exception e)
        {
            logError(e);
        }
        finally
        {
            close();
        }
    }
```
