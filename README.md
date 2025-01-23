# Scala JDBC Connection

Este proyecto demuestra cómo establecer una conexión a una base de datos MySQL usando JDBC desde Scala, y documenta los conceptos clave relacionados con JDBC y sus componentes.

## ¿Qué es JDBC y cuáles son sus componentes?

**JDBC (Java Database Connectivity)** es una API de Java que permite a las aplicaciones interactuar con bases de datos relacionales. A través de JDBC, los programas pueden ejecutar operaciones como consultas, inserciones y actualizaciones en bases de datos.

### Componentes principales de JDBC:
- **Driver JDBC**: Controlador para interactuar con la base de datos.
- **Connection**: Establece la conexión a la base de datos.
- **Statement**: Ejecuta las consultas SQL.
- **ResultSet**: Contiene los resultados de la consulta.
- **SQLException**: Maneja excepciones relacionadas con la base de datos.

Más detalles sobre JDBC pueden consultarse en [Turing](https://www.turing.com/kb/what-is-jdbc) y [Tokio School](https://www.tokioschool.com/noticias/jdbc/).

## Librerías de Scala para conectarse a una base de datos relacional

| Característica            | Slick                             | Doobie                           |
|---------------------------|-----------------------------------|----------------------------------|
| Estilo                    | Funcional + DSL SQL               | Funcional (basado en cats)       |
| Conexión a la base de datos | Proporciona su propio pool de conexiones | Usa un pool externo (HikariCP)  |
| Abstracción SQL            | Alto nivel, pero con acceso a SQL nativo | Acceso más directo a SQL        |
| Gestión de transacciones   | Soporte completo                  | Totalmente transaccional        |
| Integración con Scala      | Muy integrado en el ecosistema Scala | Requiere más configuración      |
