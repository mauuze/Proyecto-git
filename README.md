# Curso Git y GitHub
![imagen_git_github](imagenes/R.jpeg)
## Clase 1: Introducción a Git

### ¿Qué es un control de versiones?
Es un sistema que registra cada cambio que se realiza  
en el código fuente de tu proyecto.  
Esto permite tener un histórico de todos los cambios  
producidos en los ficheros.  
Básicamente, como un historial de todos los cambios que  
hiciste en tu código.  

### ¿Qué es Git?
Git es una herramienta de control de versiones diseñada por Linus Torvalds.

### ¿Qué es un repositorio?
Son el pilar de Git.  
Es una carpeta en la que se almacenan las diferentes versiones de los ficheros  
de un proyecto y también todas las versiones con los cambios que se realizaron.

### Iniciar un proyecto en Git
Existen 2 formas para crear un proyecto en Git.  
Si quieres crear un proyecto desde 0 (crear un repositorio local), puedes usar `git init` con el nombre del proyecto que quieras. Esto crea una carpeta vacía con el nombre del proyecto.  
* `git init <nombre_proyecto>`  
* `cd <nombre_proyecto>`

También puedes iniciar el proyecto desde una carpeta ya existente. Para hacerlo simplemente usas `git init` dentro de la raíz del directorio de tu proyecto.  
* `cd <directorio del proyecto>`  
* `git init`

Ambas formas sirven para poder crear un proyecto.
## Clase 2: States y Commits

### Los 3 estados de Git 
* **Modified:** El archivo fue creado, eliminado o tiene cambios que no fueron marcados como confirmados.

* **Staged:** El archivo ha sido marcado como preparado para ser confirmado en el repositorio local.

* **Committed:** El archivo se encuentra grabado en el repositorio local. Esta acción recibe el nombre de **commit**.

### Cómo cambiar el estado
Para saber el estado actual de nuestro repositorio usamos:
* `git status`

Esto nos avisará si algún archivo de nuestro repositorio recibió algún cambio.  

Si algún archivo fue modificado, nos aparecerá:

![imagen_archivo_modificado](imagenes/archivo_modificado.png)

Ahora llevaremos el archivo `README.md` al estado **staged** con el siguiente comando:
* `git add README.md`

Ahora, si volvemos a ejecutar `git status`, nos aparecerá lo siguiente:

![imagen_archivo_staged](imagenes/archivo_estado_staged.png)

Confirmando que el archivo fue movido al stage.

### ¿Qué es un commit?
Es una de las piezas más fundamentales de Git.  

Sirven para registrar los cambios realizados en nuestro repositorio. Se podría decir que son como los *checkpoints* en los videojuegos: ya tendríamos un punto al cual volver si nos equivocamos.  
Estos puntos de guardado serían nuestros commits y van firmados con un autor, fecha, localización y otra información útil.

### ¿Cómo hago un commit?
Antes de realizar un commit, nuestros cambios ya deben estar en el estado **staged**.

Para realizar un **commit**, usamos el siguiente comando:
* `git commit`

En el caso de Linux, se nos abrirá lo siguiente en la terminal:

<img src="imagenes/ventana_commit.png" alt="imagen_ventana_commit" width="650"/>

Otra manera de realizar el commit sin que se nos abra la terminal es usando el siguiente comando:
* `git commit -m "<nombre del commit>"`

De igual manera, el nombre del commit debe describir los cambios realizados en el repositorio.

Para revisar todos los commits hechos, puedes utilizar el comando:
* `git log`

### ¿Qué es el HEAD?
El **HEAD** es como una flecha que te indica "estás aquí". Solo puedes estar en un solo lugar, y ese lugar es el HEAD.  

Es el puntero que referencia el punto actual del historial de cambios del repositorio en el que estás trabajando.

### Ramas, merge y conflictos

### ¿Qué es una rama?
Una rama es una división del punto actual en el que nos encontramos en la rama principal.

### ¿Para qué sirven las ramas?
Nos sirven para hacer desarrollo no lineal y colaborativo, ya que, al poder hacer bifurcaciones de nuestro código, cada uno puede trabajar distintos aspectos de este.

<img src="imagenes/ramas.jpg" alt="imagen_ramas" width="650"/>

Como vemos en la imagen, de la rama principal salen otras 2, que serían tu trabajo y el de tu amigo, por ejemplo. Cada uno trabaja aparte y se conectan al final.

### Creando nuestra primera rama
Para crear una rama usamos el siguiente comando:
* `git branch <nombre_de_nuestra_rama>`

Ahora, para ir a nuestra rama utilizamos el comando:
* `git switch <nombre_de_nuestra_rama>`

También existe un comando que nos permite crear la rama y llevarnos directamente a esta. El comando es:
* `git switch -c <nombre_de_nuestra_rama>`

Para poder crear una rama, mínimamente debemos tener un commit en el repositorio, lo cual tiene sentido, ya que ¿cómo se podría crear una rama de algo que no tiene ni tronco?
## Clase 3: Más de ramas

### Fusionar ramas
Las divisiones que creamos en forma de rama solo tienen 2 destinos: acabar en el olvido o ser fusionada en otra rama.

**¿Pero a que nos referimos con fusion?**, cuando hablamos de funcion nos referimos a que los cambios en nuestra rama se integran con otra, de forma que el codigo que habiamos generado en la nueva rama se asimila en otra.

Para fusionar ramas empleamos el comando: 
* `git merge <nombre_rama_a_fusionar>`

Vemos que inmediatamente si solo se hicieron cambios en la rama a fusionar, pero si realizamos tanto cambios en muestra rama main como en la rama a fusionar nos sale una ventana de que se va a crear un commit de esta fusión, esto sucede porque en el primer caso se hizo un **fast-forward**.
### ¿Que es un fast-forward?
Cuando solo se hacen cambios en una rama el primer commit de la rama apunta directamente al ultimo commit de la rama main por asi decirlo, lo que hace el fast-forward es que movera el puntero de nuestro ultimo commit de la rama main al ultimo commit de nuestra rama ya que no al no hacer cambios en la rama main nuestro codigo todavia no se dividio mas que hacia la rama que hicimos.



