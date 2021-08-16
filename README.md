# Seminario MongoDB
#### Actividades sobre el uso del sistema de bases de datos Mongo DB  
***

## Actividad N° 1  

1. Instalar MongoDB en ambiente local.

~~~
- Ingresar a www.mongodb.com
- Descargar MongoDB Community Server edition.
~~~

2. Conectarse a MongoDB vía CLI.

    - Configurar la variable de entorno
    - Crear la carpeta para almacenar la db:
        ~~~
        mkdir C:\data\db
        ~~~
    - Ejecutar el servidor de Mongo en la terminal
        ~~~
        mongod
        ~~~
    - Ejecutar el cliente Mongo en otra ventana de la terminal
        ~~~
        mongo
        ~~~

        
3. Crear una nueva base de datos llamada futbolfifa.
~~~
use futbolfifa
~~~
4. Crear una nueva collection llamada players.
~~~
db.createCollection("players")
~~~
5. Insertar 5 documentos en la collection players con datos básicos
(nombre, apellido, posición, fecha de nacimiento, etc).
~~~
db.players.insert([
    {name: "Lionel", surname: "Messi", position: "forward", birthdate: new Date(24,5,1987), height: 170},
    {name: "Leandro", surname: "Paredes", position: "midfielder", birthdate: new Date(29,5,1994), height: 180}, 
    {name: "Ángel", surname: "Di María", position: "midfielder", birthdate: new Date(14,1,1988), height: 180},
    {name: "Mauro", surname: "Icardi", position: "forward", birthdate: new Date(12,1,1993), height: 181},
    {name: "Keylor", surname: "Navas", position: "goalkeeper", birthdate: new Date(15,11,1986), height: 185}])
~~~
6. Listar todos los documentos de la collection players.
~~~
db.players.find()
~~~

7. Crear otras collections con documentos (ej. teams, games, etc).

~~~
db.createCollection("teams")

db.teams.insert(
    [{name: "PSG", city: "Paris", country: "France", foundation: 1970 },
    {name: "Rayo Vallecano", city: "Madrid", country: "Spain", foundation: 1924},
    {name: "Lille", city: "Lille", country: "France", foundation: 1944}])

~~~



