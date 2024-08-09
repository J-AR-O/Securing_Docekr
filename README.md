# Proyecto Docker con Usuario No Root

Este proyecto tiene como objetivo crear contenedores Docker para una aplicación llamada "todo-app" que se ejecuta con un usuario no root. Ejecutar aplicaciones dentro de contenedores Docker sin privilegios de root es una práctica clave para mejorar la seguridad, ya que evita que el contenedor tenga permisos elevados que podrían ser aprovechados por atacantes en caso de vulnerabilidades.

## Configuración

1. **Modificar el archivo `.env`:**
   - Cambia la variable `MY_user` por el nombre de usuario que deseas utilizar dentro del contenedor, por ejemplo, `myuser`.

2. **Ajustar la configuración en `src/persistence/sqlite.js`:**
   - Asegúrate de que la configuración refleje el nombre de usuario definido en el archivo `.env`. Esto incluye verificar que la ruta del archivo SQLite en la línea 3 se ajuste correctamente al usuario especificado, por ejemplo: `/home/newuser/app/todos/todo.db`.

3. **Construir y levantar los contenedores:**
   - Ejecuta el siguiente comando para construir la imagen Docker y levantar los contenedores:
     ```bash
     docker-compose up --build
     ```

4. **Acceder a la aplicación:**
   - Una vez que los contenedores estén en funcionamiento, abre tu navegador y visita la URL:
     [http://localhost:3000](http://localhost:3000)
