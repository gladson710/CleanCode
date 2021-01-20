---
title: Classe
tags: []
---

# Classe

## Organizacao da classe

* Segundo a convencao padrao do java, uma classe deve comecar com uma lista de variaveis.
    * Variaveis
        * As publicas (public), estaticas (static) e constantes (constants), se existirem dever ser as primeiras.
        * As Variaveis estaticas privadas (private static).
        * Instancias privadas (private).
    * Metodos
        * Metodos publicos.
        * Metodos privados.
        
## As classes deve ser pequenas

* A definiciao do tamanho da classe é medido pela contagem das responsabilidades.
* É sugerido fazer o uso do Principio de responsabilidade unica.
* O nome da classe deve descrever quais responsabilidades que ela faz.

```java 
    public class Produto
    {
        private long id;
        private String nome;
        private String descricao;
        
        long getId() { ... };
        void setName { ... };
        
        String getName() { ... };
        void setName { ... };
        
        String getNDescricao() { ... };
        void setDescricao { ... };   
        
        void salva() { ... };
        void buscaProdutoPorId(long id) { ... };
    }
```

## Coesao

* Deve buscar ter uma classe com uma alta coesao. 
* As classes devem ter um pequeno numero de instancias de variaveis. 
* Cada metodo de uma classe deve manipular uma ou mais variaveis.
* Quanto mais variaveis um metodo manipular, mais coeso o metodo é para classe.

```java 
    public class Produto
    {
        private long id;
        private String nome;
        private String descricao;
        
        long getId() { ... };
        void setName { ... };
        
        String getName() { ... };
        void setName { ... };
        
        String getNDescricao() { ... };
        void setDescricao { ... };   
    }
```

```java 
    public class Produto
    {
        private long id;
        private String nome;
        private String descricao;
        
        long getId() { ... };
        void setName { ... };
        
        String getName() { ... };
        void setName { ... };
        
        String getNDescricao() { ... };
        void setDescricao { ... }; 
        
        void salva() { ... };
        void buscaProdutoPorId(long id) { ... };
    }
```
