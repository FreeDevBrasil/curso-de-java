# Parte 5 – JDBC e Interface Gráficas em Java (User Interface)

Introdução a JDBC
-----------------

JDBC é usando para principalmente para conectar ao banco de dados, mas também pode ser usado para conectar a outros 
tipos de dados, como arquivos de texto, planilhas, etc.

JDBC é uma API (Application Programming Interface) que utiliza drivers para conectar ao bancos diferentes, como
MySQL, PostgreSQL, Oracle, etc. Você tera que baixar o driver do banco de dados que você quer conectar, e adicionar
no seu projeto.

Geralmente o processo funciona assim, mas pode variar dependendo do banco de dados:

1. Registrar o driver JDBC
2. Criar uma conexão
3. Criar um statement
4. Executar uma query
5. Fechar a conexão

Veja um exemplo de como conectar ao banco de dados MySQL:

```java

import java.sql.*;

public class FirstExample {
   static final String DB_URL = "jdbc:mysql://localhost/FreeDevBrasil";
   static final String USER = "guest";
   static final String PASS = "guest123";
   static final String QUERY = "SELECT id, first, last, age FROM Employees";

   public static void main(String[] args) {
      // Open a connection
      try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
         Statement stmt = conn.createStatement();
         ResultSet rs = stmt.executeQuery(QUERY);) {
         // Extract data from result set
         while (rs.next()) {
            // Retrieve by column name
            System.out.print("ID: " + rs.getInt("id"));
            System.out.print(", Age: " + rs.getInt("age"));
            System.out.print(", First: " + rs.getString("first"));
            System.out.println(", Last: " + rs.getString("last"));
         }
      } catch (SQLException e) {
         e.printStackTrace();
      } 
   }
}
```

# Interface Gráfica em Java (User Interface ou UI)

Existem multiplas formas de criar uma interface gráfica em Java, a mais popular é Java Swing, que é uma API que contem componentes para criar botões, caixas de texto, etc. alem de `containers` para organizar os componentes, como paineis, janelas, etc.

Mas existem outras APIs, como JavaFX, GWT, ou fazer diretamente com AWT. A maioria das APIs são baseadas em AWT, uma API antiga, é continua sendo usada, e não esta indo a lugar nenhum.

As dois principais oficiais do Java são Java Swing e JavaFX e ambos são baseados em AWT. JavaFX é mais novo, e tem mais recursos, mas Swing é mais popular, e tem mais documentação.

## Java Swing

Java Swing é uma API para criar interfaces gráficas em Java, que é baseada em AWT. Swing é maduro e usada em milhares de aplicativos, e tem muito recursos disponiveis online alem da documentação mais ampla, mas Swing é mais lento que JavaFX, eventualmente não sera utilizada para aplicativos novos, mas continuara sendo usada por muito tempo para manter a compatibilidade com aplicativos antigos.

Existem multiplas ferramentas drag & drop para criar interfaces gráficas com Swing, como IntelliJ, NetBeans, Eclipse, etc. Mas você pode criar interfaces gráficas usando apenas código Java tambem.

## JavaFX

O JavaFX foi criada para subistuir o Swing para criar interfaces gráficas em Java, mas não esta indo como foi planejado, e pode utilizar os dois no mesmo aplicativo. JavaFX é mais novo, mais eficiente, e evnutalmente ultrapassara o Swing, em teremos de popularidade de uso.

-------------------------------------------------------------------

# Interfaces Gráficas alternativas, não oficiais

A maioria das interfaces alternativas que não dependem do AWT utilizam HTML de uma forma ou
outra mesmo que nem todos são acessados via browser.

## GWT (Google Web Toolkit)

## Electron com Vaadin

## Spring Web com WebJARs






































