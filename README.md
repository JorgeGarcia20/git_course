# Notas del curso de git
Creando un blog de prueba mientras hago el curso de git en platzi

## comandos de git usados en el curso
una vez creado el directorio del proyecto es turno de indicarle a git que queremos que
lleve el registro de los cambios realizados en nuestro proyecto, para ello usaremos los comandos
más básicos de git.
1. Para inicializar el repositorios debemos usar `git init`. Este comando creara un diretorio oculto donde se  almacenaran los metadatos de los cambios que realizemos en nuestro proyecto.
2. Una vez que hemos agregado o editado algun archivo debemos de ejecutar el comando `git status` el cual mostrará los cambios o modificaciones realizados en el proyecto. 
3. Ahora si que si. Nos hemos detectado los cambios pendientes por agregar, vamos a indicar a git que queremos que agregue al repositorio los cambios o archivos nuevos, para esto ejecutamos el comando `git add <nombre del archivo>` o simplemente `git add .` donde el punto indica que queremos seleccionar todo lo que esta pendiente por agregar.
4. Ya hemos indicado que queremos que git lleve el registro de los archivos agregados, ahora vamos a indicarle que una descripcion a dichos cambios, esto lo hacemos con el comando `git commit -m "descripcion de cambios o agregaciones realizadas"`

Listo con estos simples comandos hemos inicializado, consultado, agregado y commiteado nuestro repositorio.

Git cuenta con tres estados en los que es posible localizar arhivos los cuales son:
* staged: archivos que ya han sido commiteados pero aun no son enviados al repositorio remoto, si no que estan en el repositorio local.
* modified: archivos que han sido modificados.
* commited: archivos que ya han sido agregados y asignado una descripcion.

# git rm
Supongamos que ya hemos realizado cambios y los hemos agregado con el comando `git add` pero nos hemos dado cuenta que aun no estan listos los cambios que teniamos asignado por hacer.

Si ejecutamos el comando `git status` nos moestrara que los cambios que hemos realizado estan en en estado `modified`

Si ejecutamo el comando `git rm <nombre del archivo> --cached` lo que haremos sera regresar el estado del archivo de `modified` a `untracked` sin hacer afectado el contenido del archivo.

Una vez ralizados los cambios pendientes ahora si podemos volver a agregar con `git add` y realizar un commit.

# git reset
Suponiendo que queremos regresar a una version anterior del proyecto el comando que nos puede ayudar a realizar esta accion es el comando reset el cual es algo peligroso si no es usado con cuidado.
git reset tiene dos opciones --soft y --hard. si utulizamos este comando con la opcion --hard vamos a regresar en el tiempo a la version que indiquemos y habremos eliminado todos los cambios posteriores.

Para indicar que version queremos retornar usaremos el comando `git log` el cual mostrara la descripcion de cada cambio realizado y un hash que es el identificador de deterninado cambio. Lo que haremos será copiar parte o en su totalidad de dicho hash y lo colocaremos despues en el comando reset como se muestra a continuación:
`git reset --hard <hash>`

Si no queremos perder los cambios realizados y que estan en el estado modified unicamente cambiamos la opcion `--hard` por `--soft` y listo.


