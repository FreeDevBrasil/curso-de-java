# Parte 1 - Introdução a Java, e Orientação a objetos em geral

* [Introdução á JAVA](#introduo--java)
* [Os 4 pilares da programação orientada a objetos](#os-4-pilares-da-programao-orientada-a-objetos-)
    * [Abstração](#abstrao)
    * [Encapsulamento](#encapsulamento)
    * [Herança](#herana)
    * [Polimorfismo](#polimorfismo)

## Introdução á JAVA

* Antes de começar, [Java](https://bit.ly/java-orientacao-objetos) não tem nenhuma relação com [Javascript](https://bit.ly/java_is_not_javascript), além do nome.
  São duas linguagens totalmente diferentes que servem propósitos diferentes. Essa semelhança de nomes confunde muitos, e infelizmente,
  [a história não é nem interessante](https://bit.ly/js_nome).

* Java é utilizada em todas as industrias globais de multiplas formas diferentes, equipamentos de  últiplos tipos. Além disso Java é a principal língua do [Android](), além de ser utilizada para programar cartões de SIM (chip telefônicos para celulares. Embora Java não esteja muito presente em desenvolvimento de Jogos em geral, um dos mais populares jogos de todos os tempos foi escrito em Java. Então, Java esta em todos os lugares.

* Sintaxe é simples e familiar. Java faz parte da família das linguagens do C, junto com dezenas outras como C/C++, Objective-C, JavaScript/TypeScript, PHP, etc. Além do fato que Java é muito consistente de estrutura e formatação de nomes no sintaxe para classes, meteodos e variaveis.

* Gerneciamento de memoria automatica pelo coletor de lixo de alta qualidade, que alem de pode ser configurado, pode extender ou trocar por seu proprio.

* Biblioteca padrão embutita é ampla é vem com "pilhas inclusas". Mas no caso que precise utilizar uma biblioteca externa, Java tem um suporte a gerenciamento excelente de bibliotecas via Maven. Considerado um dos melhores, especialmente em comparação a NPM ou Composer.

* Suporta nativamente UTF-8, além de JNI que permite que código rodando no JVM consegue integrar (bi-direcionalmente) com código nativo, escrito em C/C++ e compilado em Assembly.

* Suporte de programação distribuida ou multipcoessamento foi bem planejado em Java e considerado mais practico em ] uso se comparar com outras linguas como Python, ou C/C++.

* O código em execução pode seR alterado dinamicamente, por que as classes são armazenadas independentemente e podem ser carregadas no momento de utilização, ou subistuidas.

* Ferramentas de desenvolvimento são excelementes em termos de analize, auto-completação, que aumenta a produtividade.

* Tem excelent suprte ao controle de qualidade, não apenas por testes unitários e JUnit, mas Java tem ampla caixa de ferramentas para testes automaticos.

* Java é uma linguagem [Orientada a Objetos](https://pt.wikipedia.org/wiki/Orienta%C3%A7%C3%A3o_a_objetos), aonde criamos objetos virtuais, que as vezes representam objetos da vida real, mas são usados de outras formas tambem. Mas Programação orientada a objetos é muito mais do que só isso.

## Os **4 pilares da programação orientada a objetos**:

### Abstração

Abstrair algo significa esconder os detalhes da implementação dentro de algo – às vezes um protótipo, às vezes em uma função. Portanto, quando você chama a função, não precisa entender exatamente o que ela está fazendo.

Um exemplo claro do conceito de abstração seria o funcionamento de um carro. Quando acionamos ele para ligar, não precisamos saber quais passos ele faz para colocar o motor em funcionamento. Quando acionamos o freio, não precisamos saber todos os mecanismos que são acionados para fazer o carro frear. Apenas sabemos o que cada objeto ou função do carro produz como resultado.

### Encapsulamento

A definição de encapsulamento é "a ação de colocar algo dentro ou como se estivesse em uma cápsula". Remover o acesso a partes do seu código e tornar as coisas privadas é exatamente o que o Encapsulamento faz (muitas vezes, as pessoas se referem a ele como "ocultação de dados").

Encapsulamento significa que o código de cada objeto deve controlar apenas seu próprio estado.  Se você não sabe o que é o estado de um objeto, vamos fazer a seguinte analogia:

Sabe aquele retrato de família, em que você era bebê ainda? Ele é um registro do estado "instantâneo" em que você estava naquele exato momento. De lá pra cá muita coisa mudou, e se hoje você tirar uma nova foto, seu estado já não é o mesmo que aquele. Aquilo que você fez durante o tempo com sua vida, transformou você. A mesma coisa ocorre com o objeto.

O estado é o "instantâneo" atual do objeto. Todas as chaves e métodos (funções) de um objeto são suas propriedades. Se você redefinir ou excluir uma chave, por exemplo, estará alterando o seu estado.

Por isso, é importante limitar o acesso de quais partes do código podem ser acessadas. Caso não sejam necessárias, torne as coisas mais inacessíveis para não possibilitar efeitos colaterais no estado do objeto.

### Herança

A herança permite que um objeto adquira as propriedades e métodos de outro objeto. Em JavaScript, isso é feito por Prototypal Inheritance (ou herança prototípica, em português).

A reutilização é o principal benefício aqui. Sabemos que às vezes a mesma coisa precisa ser feita em vários lugares e sempre de forma igual, exceto em alguma pequena parte. Esse é um problema que a herança pode resolver.

![inheritance](https://user-images.githubusercontent.com/5832718/209377805-0aac1e3d-8aed-45ec-875e-0f4374900830.png)

### Polimorfismo

Polimorfismo significa "a condição de ocorrer de várias formas diferentes". É exatamente com isso que o quarto e último pilar está preocupado – que tipos nas mesmas cadeias de herança sejam capazes de fazer coisas diferentes.

Se você usou a herança corretamente, agora pode usar tanto os pais de maneira confiável como seus filhos. Quando dois tipos compartilham uma cadeia de herança, eles podem ser usados ​​alternadamente sem erros ou declarações em seu código.

Portabilidade - Independência de plataforma - "escreva uma vez, execute em qualquer lugar" ("write once, run anywhere");
Recursos de Rede - Possui extensa biblioteca de rotinas que facilitam a cooperação com protocolos TCP/IP, como HTTP e FTP;
Segurança - Pode executar programas via rede com restrições de execução.

Para entender melhor o Polimorfismo, considere o código a baixo:

```java

public abstract class Animal {
    protected String nome;
    protected Animal(String nome) { this.nome = nome; }
    public String getNome() { return nome; }
    public void setNome(String nome) { this.nome = nome; }
}

public class Gato extends Animal {
    protected int idade;
    public Gato(String nome) { super(nome);}
    public int getIdade() { return idade; }
    public void setIdade(int idade) { this.idade = idade; }
}

Animal meuAnimal = new Gato("Billy"): // Isso é OK, por que um Gato é Animal.

Gato meuGato = new Animal("Billy"): // Isso NÃO é OK, por que nem tudo Animal é Gato.

```

Mas isso é apenas um lado do polimorfismo e eu recomendo esse artigo para entender perfeitamente: [Uso de Polimorfismo em Java](https://www.devmedia.com.br/uso-de-polimorfismo-em-java/26140)
