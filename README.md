# TRABAJO DE CONSULTA: Conexión base de datos relacional

Este proyecto demuestra cómo establecer una conexión a una base de datos MySQL usando JDBC desde Scala, y documenta los conceptos clave relacionados con JDBC y sus componentes.

## ¿Qué es JDBC y cuáles son sus componentes?

**JDBC (Java Database Connectivity)** es una API de Java que permite a las aplicaciones interactuar con bases de datos relacionales. A través de JDBC, los programas pueden ejecutar operaciones como consultas, inserciones y actualizaciones en bases de datos. Es decir es una interfaz que permite que programas escritos en Java se conecten y realicen operaciones sobre bases de datos. Funciona en cualquier sistema operativo y con cualquier base de datos, usando SQL para interactuar con los datos. En términos sencillos, JDBC actúa como un puente que permite que Java se comunique de manera estándar con distintas bases de datos, sin preocuparse por las diferencias de cada una.


### Componentes principales de JDBC:
- **Driver JDBC**: Controlador para interactuar con la base de datos. Permite que Java entienda y ejecute los comandos SQL que la base de datos requiere.
- **Connection**: Establece la conexión a la base de datos. Es el objeto que establece y gestiona la comunicación entre la aplicación Java y la base de datos. 
- **Statement**: Ejecuta las consultas SQL. A través de él, puedes pedir datos, hacer modificaciones o ejecutar procedimientos almacenados.
- **ResultSet**: Contiene los resultados de la consulta. Es donde se almacenan los datos obtenidos de una consulta. Permite acceder a los resultados y recorrer los datos fila por fila.
- **SQLException**: Maneja excepciones relacionadas con la base de datos. Es una clase que maneja errores relacionados con la base de datos, como problemas de conexión o errores en las consultas SQL.

# Librerías de Scala para Conectarse a una Base de Datos Relacional

En Scala, existen varias librerías y frameworks que permiten conectarse a bases de datos relacionales. A continuación, se detallan algunas de las más populares:

## 1. JDBC (Java Database Connectivity)

Scala es completamente compatible con Java, por lo que se puede utilizar JDBC para conectarse a bases de datos relacionales. Aunque no es específico de Scala, JDBC es una opción robusta y ampliamente utilizada.

### Ejemplo básico de JDBC:
```scala
import java.sql._

val conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/mi_base", "usuario", "contraseña")
val stmt = conn.createStatement()
val rs = stmt.executeQuery("SELECT * FROM tabla")

while (rs.next()) {
  println(rs.getString("columna"))
}

conn.close()
```

## 2.  Slick

Slick es una librería de Scala que proporciona una interfaz funcional y escalable para interactuar con bases de datos relacionales. Es más elegante que JDBC y facilita la consulta y manipulación de datos utilizando una API de alto nivel.

### Ejemplo básico de JDBC:

```scala
import slick.jdbc.MySQLProfile.api._

val db = Database.forConfig("mydb")
val query = TableQuery[MiTabla]

val action = query.result
val result = db.run(action)

result.map { rows =>
  rows.foreach(println)
}
```

## 3. Doobie

Doobie es una librería funcional para trabajar con bases de datos SQL en Scala. Está basada en el paradigma funcional y permite la ejecución de consultas SQL dentro de un contexto monádico.

```scala 
### Ejemplo básico de JDBC:
import doobie._
import doobie.implicits._
import cats.effect.IO

val xa = Transactor.fromDriverManager[IO](
  "com.mysql.cj.jdbc.Driver", 
  "jdbc:mysql://localhost:3306/mi_base", 
  "usuario", 
  "contraseña"
)

val query = sql"SELECT * FROM tabla".query[String]
val result = query.to[List].transact(xa).unsafeRunSync()

result.foreach(println)

```



## REFERENCIAS 
- colaboradores de Wikipedia. (2025, 15 enero). Java Database connectivity. Wikipedia, la Enciclopedia Libre. https://es.wikipedia.org/wiki/Java_Database_Connectivity
- 
