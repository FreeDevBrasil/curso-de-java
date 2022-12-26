# Parte 2 - Tipos primitivos, classes e objetos e a diferencia entre eles.

## Tipos primitivios

Existem 8 (ou 9 se consideramos como um tipo primitivo) tipos primitivos em Java. Essas variaveis NÃO são objetos mas são tipos mais
básicos, e especificam apenas o tamanho e a categoria de valores de variáveis e não contem métodos adicionais. 

Cada um dessses tipos primitivos tem uma classe específica para criar objetos do valor do tipo primitivo, e essas 
classes são chamadas "wrapper". Por exemplo, o tipo primitivo `int` tem uma classe wrapper chamada `Integer`. E a 
classe `Integer` tem metodos para manipular, alterar, etc... o valor do `int` que a classe `Integer` guarda por dentro.

O beneficio é que podemos evolver a utilidade de um valor primitivo usando a classe wrapper, de tal tipo.

### Outros beneficios de uso de classes wrapper

1. Eles convertem tipos de dados primitivos em objetos. Os objetos são necessários se quisermos modificar os argumentos 
   passados para um método (porque os tipos primitivos são passados por valor).


2. As classes no pacote java.util lidam apenas com objetos e, portanto, as classes wrapper também ajudam nesse caso.
   * Classes comuns como List, Map, Set, Collection, ArrayList e Vector, e muitos outros armazenam apenas 
     objetos e não tipos primitivos. O motivo é que essas classes trabalhar com tipos de referência, que podem ser
     alterados dentro do método, mas tipos primitivos não podem ser alterados dentro do método, para alterar valor de um
     tipo primitivo, tem que re-assignar um novo valor ao variavel.


3. Um objeto é necessário para oferecer suporte à sincronização em multithreading.


### Então, agora sabemos que as principais diferenças entre tipos primitivos e wrappers são:

1. Os tipos primitivos são mais rápidos que os wrappers, por não ser objetos. Mas isso depende do JDK (ou JVM) usado, 
   por que alguns JVMs otimizam o uso de wrappers, e convertem para tipos primitivos quando possível, e outros não.


2. Os tipos primitivos não podem ser nulos, mas objetos podem ser nulos. Todos os tipos primitivos têm um valor
   padrão se não for inicializada. Por exemplo, um `int` é 0, um `boolean` é false, um `char` é '\u0000'.


3. Os tipos primitivos não têm métodos, mas os wrappers têm métodos. Primitivos podem ter propriedades, mas não métodos.


4. Tipos primitivos são predefinidos (por exemplo, `int`, `boolean`, `char`), e não é possivel criar um tipo primitivo.
   Pode criar classes, interfaces, enums ou annotations que utilizam tipos primitivos internamente, mas não pode criar
   um tipo primitivo.

<table>
    <thead>
        <tr>
            <th>Categoria</th>
            <th>Tipo</th>
            <th>Wrapper</th>
            <th>Tamanho <br>byte / bits</th>
            <th>Min</th>
            <th>Max</th>
            <th>Exemplo de uso</th>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td rowspan="5">Integer</td>
        <td>byte</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Byte.html">Byte</a></td> 
        <td>1 byte (8 bits)</td>
        <td>-128</td>
        <td>127</td>
        <td><pre>byte b = 65;</pre></td>
    </tr>
    <tr>
        <td>char</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Character.html">Character</a></td>
        <td>2 bytes (16 bits)</td>
        <td colspan="2">Um caracter Unicode</td>
        <td><pre>char c = 'A';</pre></td>
    </tr>
    <tr>
        <td>short</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Short.html">Short</a></td>
        <td>2 bytes (16 bits)</td>
        <td>-32.768</td>
        <td>32.767</td>
        <td><pre>short s = 65;</pre></td>
    </tr>
    <tr>
        <td>int</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Integer.html">Integer</a></td>
        <td>4 bytes (32 bits)</td>
        <td>-2.147.483.648</td>
        <td>2.147.483.647</td>
        <td><pre>int i = 65;</pre></td>
    </tr>
    <tr>
        <td>long</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Long.html">Long</a></td>
        <td>8 bytes (64 bits)</td>
        <td>-9.223.372,03.854.775.808</td>
        <td>9.223.372.036.854.775.807</td>
        <td><pre>long l = 65L;</pre></td>
    </tr>
    <tr>
        <td rowspan="2">Floating Point</td>
        <td>float</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Float.html">Float</a></td>
        <td>4 bytes (32 bits)</td>
        <td>3,40282347 x 10<sup>38</sup></td>
        <td>1,40239846 x 10<sup>-45</sup></td>
        <td><pre>float f = 65f;</pre></td>
    </tr>
    <tr>
        <td>double</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Double.html">Double</a></td>
        <td>8 bytes (64 bits)</td>
        <td>1,7976931348623157 x 10<sup>308</sup></td>
        <td>4,9406564584124654 x 10<sup>-324</sup></td>
        <td><pre>double = d = 65.55;</pre></td>
    </tr>
    <tr>
        <td colspan="7" style="color: #b43131">Lembre-se: <strong>float</strong> e <strong>double</strong> NUNCA podem ser usados para tratar
        valores moneatarios. Não importa se usa wrapper ou não. Existem classes especificas para isso. </td>
    </tr>
    <tr>
        <td rowspan="2">Outros</td>
        <td>boolean</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Boolean.html">Boolean</a></td> 
        <td>1 byte (8 bits)</td>
        <td>false</td>
        <td>true</td>
        <td><pre>boolean b = false;</pre></td>
    </tr>
    <tr>
        <td>void</td>
        <td><a href="https://docs.oracle.com/en/java/javase/19/docs/api/java.base/java/lang/Void.html">Void</a></td> 
        <td colspan="4">Void não tem nem valor ou tamanho especifico. Normalmente usado para indicar metodos sem valor
        de retoorn</td>
    </tr>
    </tbody>
</table>

## Classes e Objetos em Java

A diferença entre uma classe e um objeto é que uma classe é um modelo para um objeto. Um objeto é apenas uma instância 
criada de uma classe. Uma classe é uma categoria de dado, e um objeto é uma variavel do tal classe. Ou seja, a classe
é uma receita de bolo, e o objeto é o bolo.

### Criando uma classe representando um carro

Para criar uma classe em Java, basta usar a palavra reservada `class` seguida do nome da classe. Por convenção, o nome
da classe deve começar com letra maiuscula. A classe pode conter atributos e metodos. Atributos são variaveis que pertencem
a classe, e metodos são funções que pertencem à classe. A classe pode conter atributos e metodos privados, protegidos e
publicos. Atributos e metodos privados só podem ser acessados na classe. Atributos e metodos protegidos só podem ser
acessados na classe e de classes filhas. Atributos e metodos publicos podem ser acessados de qualquer lugar.

```java

// Definição de uma classe chamada Carro.

public class Carro {
    
    private String marca;
    private String modelo;
    private int ano;
    
    public void ligar() {
        this.ligado = true;
    }
    
    public void desligar() {
        this.ligado = false;
    }
    
    public void imprimir() {
        System.out.println("Marca: " + this.marca);
        System.out.println("Modelo: " + this.modelo);
        System.out.println("Ano: " + this.ano);
        System.out.println("Ligado: " + this.ligado);
    }
}

// Criação de um objeto da classe Carro.

Carro carro = new Carro();
carro.imprimir(); // Vai imprimir os valores padrão dos atributos da classe Carro.
```
    
