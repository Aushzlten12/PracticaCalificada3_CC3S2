# Practica Calificada 3 - Respuestas

##  Empezando a trabajar con Rails

### Preguntas

- ¿Cómo decide Rails dónde y cómo crear la base de datos de desarrollo? (Sugerencia: verifica los subdirectorios db y config)

Rails decide eso en el archivo `/config/database.yml` con las siguientes lineas de codigo.

```yml
development:
  <<: *default
  database: db/development.sqlite3
```

Y como podemos ver en el directorio `db/` existe el archivo `development.sqlite3`. 

- ¿Qué tablas se crearon mediante las migraciones?

Se creo la tabla **movies** ya que en en la migracion *CreateMovies* se ha definido un método para crear dicha tabla y sus campos. Para poder visualizar esto, podriamos ejecutar `sqlite3 db/development.sqlite3` esto nos habilitara una consola de comandos SQLite.

```sql
SQLite version 3.43.1 2023-09-11 12:01:27
Enter ".help" for usage hints.
sqlite> .tables
movies             schema_migrations
sqlite> 
```

- ¿Qué datos de semilla se insertaron y dónde se especificaron? (Pista: rake -T db:seed explica la tarea de semilla, rake -T explica otras tareas de Rake disponibles)