# Curso Git y GitHub
![imagen_git_github](imagenes/R.jpeg)
## Clase 1: Introduccion a Git
### ¿Que es un control de versiones?
Es un sistema que registra cada cambio que se realiza 
en el codigo fuente de tu proyecto.
Esto permite tener un historico de todos los cambios 
producidos en los ficheros.
Basicamente como un historial de todos los cambios que 
hiciste en tu codigo. 
### ¿Que es git?
Git es una herramienta de control de versiones diseñado por Linus Torvalds.
### ¿Que es un repositorio?
Son el pilar de git.

Es una carpeta en la que se almacenan las diferentes versiones de los ficheros 
de un proyecto y tambien todas las versiones que con los cambios que se realizaron.
### Iniciar un proyecto en git
Existen 2 formas para crear un proyecto en git.
Si quieres crear un proyecto desde 0 (crear un repositorio local), puedes usar `git init` con el nombre del proyecto qur quieras. Esto crea una carpeta vacia con el nombre del proyecto.
* ` git init <nombre_proyecto> ` 
* `cd <nombre_proyecto>`

Tambien puedes iniciar el proyecto desde una carpeta ya existente. Para hacer simplemente usas `git init` dentro de la raiz del directorio del tu proyecto.
* `cd <directorio del proyecto>`
* `git init`

Ambas formas sirven para poder crear un proyecto.
## clase 2: States y commits
### Los 3 estados de git 
* **Modified:** El archivo fue creado, eliminado o este tiene cambios que no fueron marcados como confirmados.

* **Staged:** El archivo has sido marcado como preparado para ser confirmado en el repositorio local.

* **Commited:** El archivo se encuentra grabado en el repositorio local. Esta accion recibe el nombre de **commit**.

### Como cambiar el estado
Para saber el estado actual de nuestro repositorio usamos
* `git status`

esto nos avisara si algun archivo de nuestro repositorio recibio algun cambio 

Si algun archivo fue modificado nos aparecera:

![imagen_archivo_modificado](imagenes/archivo_modificado.png)

Ahora llevaremos el archivo README.md al estado **staged** con el siguiente comando:
* `git add` README.md

Ahora si volvemos a ejecutar el `git status` no aparecera lo siguiente:

![imagen_achivo_staged](imagenes/archivo_estado_staged.png)

confirmando que el archivo fue movido al stage.

### ¿Que es un commit?
Es una de las piezas mas fundamentales de Git.

Sirven para registrar los cambios realizados en nuestro respositorio, se podria decir que son como los checkpoints en los videojuegos ya tendriamos un punto al cual volver si nos equivocamos. Estos puntos de guardado serian nuestros commits y van firmados con un autor, fecha, localizacion y otra informacion util.

### ¿Como hago un commit?
Antes de realizar un commit nuestros cambios ya deben estar en la estado **staged**.

Para realizar un **commit** realizamos el siguiente comando:
* `git commit` 

en el caso de Linux se nos abrira lo siguiente en la terminal:

<img src="imagenes/ventana_commit.png" alt="imagen_ventana_commit" width="650"/>

Otra manera de realizar el commit sin que se nos abra la terminal, podemos usar el siguiente comando:
* `git commit -m <"nombre del commit>` 

De igual manera el nombre del commit debe describir los cambios realizados en el repositorio.

Para revisar todos los commits hechos puedes utilizar el comando: 
 * `git log`

### ¿Que es el HEAD?
El **HEAD** es como un flecha que te indica "estas aqui". Solo puedes estar en un solo lugar y ese lugar es el HEAD.

Es el puntero que referencia el punto actual del historial de cambios del repositorio en el que estas trajando.
### Ramas, merge y conflictos
### ¿Que es una rama?
Una rama es una division del punto actual en el que nos encontramos en la rama principal.
### ¿Para que siven las ramas?
Nos sirven hacer desarrollo no lineal y colaborativo, ya que al poder hacer bifuraciones de nuestro codigo cada uno puede trabajar distintos aspectos de este.

<img src="imagenes/ramas.jpg" alt="imagen_ramas" width="650"/>

### Creando nuestra primera rama
Para crear una rama usamos el siguiente comando:
 * `git branch <nombre_de_nuestra_rama>`

 Ahora para ir a nuestra rama utilizamos el comando:
 * `git switch <nombre_de_nuestra_rama>`

 Tambien existe un comando que nos permite crear la rama y llevarnos directamente a esta, el comando es:
* `git switch -c <nombre_de_nuestra_rama>`

Para poder crear una rama minimamente debemos tener un commit en el repositorio, lo cual tiene sentido ya que como se podria crear una rama de algo que no tiene ni tronco.

