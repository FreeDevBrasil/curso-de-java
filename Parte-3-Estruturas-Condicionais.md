# Parte 3 - Estrutras Condicionais

## Introdução

Estruturas condicionais, são utilizadas para executar um bloco de código somente se uma condição for verdadeira, 
ou seja, se a condição for falsa, o bloco de código não será executado. Mas tambem podemos executar um bloco de código
se a condição for falsa, utilizando o `else` por exemplo (existem outros metodos que serão explicadas tambem).

## Estruturas condicionais

### if, else-if, else

A estrutura condicional `if` é utilizada para executar um bloco de código somente se uma condição for verdadeira.

```java
if (condicao) {
    // bloco de código a ser executado se a condição for verdadeira
}
```

A condição deve ser um valor booleano, ou seja, `true` ou `false`.

```java

int x = 10;

if (x > 5) {
    System.out.println("x é maior que 5");
}

```

A estrutura condicional `else-if` é utilizada para executar um bloco de código se uma condição for verdadeira, e outro
bloco de código se a condição for falsa.

```java
if (condicao) {
    // bloco de código a ser executado se a condição for verdadeira
} else {
    // se não, esse bloco de código sera executado
}

int x = 10;

if (x > 5) {
    System.out.println("x é maior que 5");
} else {
    System.out.println("x é menor ou igual a 5");
}
```
