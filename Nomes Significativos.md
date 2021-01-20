---
title: Nomes Significativos
tags: []
---

# Nomes Significativos de variaveis

* Escolher bons nomes leva tempo, quanto melhor for esse nomes mas facil será a leitura do codigo.
* Troque os nomes quando encontrar nomes melhores.

## Usar nome que revelam seu proposito.

### Exemplo 1:

**Ruim:**
```java 
    int d; //tempo decorrido em dias
```
** Bom:**
```java  
    int tempoDecorridoEmdias;
```

## Evite informacoes erradas. 

* Os programadores deve evitar passar dicas ou ideias falsas que confudam o sentido do codigo.
    
** Ruim:**
```java
    Set accountList;
    
    int numeroXP; // Nao é numero de ponto de experiencia
    int numeroDoCSU; // Nao e caso de uso
```  
** Bom:**
```java  
    Set accounts;
    
    int numeroX..P..; // Nao use abreviaturas
    int numeroDoCodigoS..U..; // Nao use abreviaturas
```

## Faca distincoes significativas.
 
** Ruim:**
```java      
    //Exemplo1
    ProdutoInfo produtoInfo;
    ProdutoDados produtoDados;
    
    //Exemplo2
    getContasAtivasDados();
    getContasAtivasInfo();

    //Exemplo3
    public String concatenaNomeSobrenome(String nome, String sobrenome)
    {
        String umNome = nome.trim();
        String umSobrenome = sobrenome.trim();
        
        return umNome + " " + umSobrenome;
    }   

```  
** Bom:**
```java
    //Exemplo3
    public String concatenaNomeSobrenome(String nome, String sobrenome)
    {
        String nomeSemEspacosLaterais = nome.trim();
        String sobrenomeSemEspacosLaterais = sobrenome.trim();
        
        return umNome + " " + umSobrenome;
    }   
```  
  
## Use nomes pronunciaveis.

* Nomes devem ser faceis de pronunciar.

** Ruim:**
```java 
    Date ymdhmsDaGeracao;
    Date ymdhmsDaAlteracao;
```      
 ** Bom:**
```java     
    Date dataHoraDaGeracao;
    Date dataHoraDaAlteracao;
```   

## Use nomes passiveis de busca

** Ruim:**
```java 
    setTransacao(descricao, tipo, 84000001); // 84000001 é chamado de numero magico
```      
 ** Bom:**
``` java     
   public static final int CODIGO_DE_TRANSACAO = 84000001;

   setTransacao(descricao, tipo, CODIGO_DE_TRANSACAO);;
```

## Adicione um contexto significativo.

** Exemplo:**
```java 
    String cidade; // Sem contexto
    String estado; // Sem contexto
    
    String enderecoCidade; // Evitar
    String enderecoEstado; // Evitar
    enderecoCliente.cidade; // Crie uma classe
    enderecoCliente.estado; // Crie uma classe
```

# Nomes Significativos de interfaces e implementacoes

* O **"I"** no inicio, tao comum hoje em dia, é na melhor das hipoteses uma distracao, e na pior sao informacoes excessivas.
 
** Comum:**
``` java    
IParticaoVariavel iParticaoVariavel = new ParticaoVariavelImpl();
```    
 ** Sugerido:**
``` java    
ParticaoVariavel particaoVariavel = new ParticaoVariavelImpl();
ParticaoVariavel particaoVariavel = new CParticaoVariavel();
```    
# Nomes de classes

* Classes e objectos devem ter nomes com substantivo(s).
* Evitar palavras com Gerente, Processador, Dados ou Info no nome da clase

** Evitar:**
``` java    
    ClienteInfo
    CartaoDados
```

 ** Validos:**
``` java    
    Cliente
    Cartao
    ContaCorrente
    ContaPoupanca
```
# Nomes de metodos

* Devem ter verbos na composicao do nome.
* Devem-se nomear metodos de acesso, alteracao e autenticacao segundo seus valores e adicionar os prefixos get, set ou is de acordo
com o padrao java bean.
* Selecione uma palavra por conceito abstrato e fique com ela. Exemplo: Escolher entre pegar, obter, recuperar.
* Adicione um contexto significativo.

** Exemplos:**
``` java    
    calculaImpostoDeImportacao();
    obtemConta();

    obterConta();
    adicionarCliente();
    salvar();

    getContaCorrente();
    isCartaoBloqueado();
```
