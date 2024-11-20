## Database connection using Java

### 1. MY SQL

MySQL is an open-source relational database management system that is widely used for web applications and other types of software systems. To connect Java applications with MySQL, you need to use a JDBC (Java Database Connectivity) driver. 
JDBC is a Java API that provides standard methods for connecting to databases and executing SQL statements.
To connect to a MySQL database, you need to know the hostname, username, password, and database name. With this information, you can create a JDBC URL and use the DriverManager class to establish a connection to the database. 
Once you have a connection, you can execute SQL statements using the Statement or PreparedStatement interfaces.

```java
import java.sql.*;

public class MySQLConnection {
    public static void main(String[] args) {
        String host = "jdbc:mysql://localhost:3306/mydatabase";
        String username = "root";
        String password = "password";
        try {
            Connection conn = DriverManager.getConnection(host, username, password);
            System.out.println("Connected to MySQL database");
        } catch (SQLException e) {
            System.out.println("Failed to connect to MySQL database");
            e.printStackTrace();
        }
    }
}

```

### 2. Oracle

Oracle is a widely used commercial relational database management system. Like MySQL, Oracle also uses JDBC to connect Java applications to the database. 
To connect to an Oracle database, you need to have the Oracle JDBC driver installed on your system.
To connect to an Oracle database, you need to know the hostname, port number, SID (System Identifier), username, and password.
With this information, you can create a JDBC URL and use the DriverManager class to establish a connection to the database.

```java
import java.sql.*;

public class OracleConnection {
    public static void main(String[] args) {
        String host = "jdbc:oracle:thin:@localhost:1521:orcl";
        String username = "user";
        String password = "password";
        try {
            Connection conn = DriverManager.getConnection(host, username, password);
            if (conn != null) {
                System.out.println("Connected to Oracle database");
                stmt = conn.createStatement();
                String QUERY = "SELECT EMPID, FIRSTNAME, LASTNAME FROM EMPLOYEE";
                ResultSet rs = stmt.executeQuery(QUERY);
                while(rs.next()){
                    //Display values
                    System.out.print("EMPID: " + rs.getInt("EMPID"));
                    System.out.print(", FIRSTNAME: " + rs.getString("FIRSTNAME"));
                    System.out.println(", LASTNAME: " + rs.getString("LASTNAME"));
                }
            }
        } catch (SQLException e) {
            System.out.println("Failed to connect to Oracle database");
            e.printStackTrace();
        }
    }
}
```


### 3. PostgreSQL

PostgreSQL is an open-source relational database management system that is widely used for web applications and other types of software systems and is known for its reliability, performance, and security. 
Like MySQL and Oracle, PostgreSQL also uses JDBC to connect Java applications to the database.
To connect to a PostgreSQL database, you need to have the PostgreSQL JDBC driver installed on your system. To connect to a PostgreSQL database, you need to know the hostname, port number, database name, username, and password. 
With this information, you can create a JDBC URL and use the DriverManager class to establish a connection to the database.

```java
import java.sql.*;

public class PostgreSQLConnection {
    public static void main(String[] args) {
        String host = "jdbc:postgresql://localhost:5432/mydatabase";
        String username = "user";
        String password = "password";
        try {
            Connection conn = DriverManager.getConnection(host, username, password);
            System.out.println("Connected to PostgreSQL database");
        } catch (SQLException e) {
            System.out.println("Failed to connect to PostgreSQL database");
            e.printStackTrace();
        }
    }
}
```

