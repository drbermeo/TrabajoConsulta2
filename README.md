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

Más detalles sobre JDBC pueden consultarse en [Turing](https://www.turing.com/kb/what-is-jdbc) y [Tokio School](https://www.tokioschool.com/noticias/jdbc/).

## Librerías de Scala para conectarse a una base de datos relacional

| Característica            | Slick                             | Doobie                           |
|---------------------------|-----------------------------------|----------------------------------|
| Estilo                    | Funcional + DSL SQL               | Funcional (basado en cats)       |
| Conexión a la base de datos | Proporciona su propio pool de conexiones | Usa un pool externo (HikariCP)  |
| Abstracción SQL            | Alto nivel, pero con acceso a SQL nativo | Acceso más directo a SQL        |
| Gestión de transacciones   | Soporte completo                  | Totalmente transaccional        |
| Integración con Scala      | Muy integrado en el ecosistema Scala | Requiere más configuración      |
## REFERENCIAS 
- colaboradores de Wikipedia. (2025, 15 enero). Java Database connectivity. Wikipedia, la Enciclopedia Libre. https://es.wikipedia.org/wiki/Java_Database_Connectivity
- 
