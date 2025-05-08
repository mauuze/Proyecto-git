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
Las divisiones que creamos en forma de rama solo tienen dos destinos: acabar en el olvido o ser fusionadas en otra rama.

**¿Pero a qué nos referimos con fusión?**  
Cuando hablamos de fusión nos referimos a que los cambios en nuestra rama se integran con otra, de forma que el código que habíamos generado en la nueva rama se asimila en otra.

Para fusionar ramas empleamos el comando: 
* `git merge <nombre_rama_a_fusionar>`

Vemos que la fusión ocurre inmediatamente si solo se hicieron cambios en la rama a fusionar.  
Pero si realizamos cambios tanto en nuestra rama `main` como en la rama a fusionar, nos aparece una ventana indicando que se va a crear un commit de fusión.  
Esto sucede porque en el primer caso se hizo un **fast-forward**.

Cuando solo se hicieron cambios en la rama a fusionar, la salida será como se muestra en la siguiente imagen.

![imagen_fast_forward](imagenes/fast-forward.png)

Cuando se hicieron cambios tanto en la rama main como en la rama que creamos, al momento de hacer el merge se nos abrirá lo siguiente en la terminal:

<img src="imagenes/fusion_varios_cambios_ramas.png" alt="fusion_varios_cambios_ramas." width="650"/>

En mi caso, donde dice Merge branch "ramita", se indica el nombre que se le asignará al commit de fusión.

### ¿Qué es un fast-forward?
Cuando solo se hacen cambios en una rama, el primer commit de esta apunta directamente al último commit de la rama **main**, por así decirlo.  
Lo que hace el fast-forward es mover el puntero del último commit de la rama **main** al último commit de nuestra nueva rama, ya que, al no haber cambios en **main**, nuestro código no se dividió realmente, más allá de la rama que creamos.

### ¿Por qué no se crea el fast-forward cuando hacemos cambios en el main?
Se podría decir que, al momento de hacer cambios en nuestra rama **main**y en la otra rama, se forman dos caminos distintos desde el último commit antes de crear la rama.  
Entonces, para poder volver al camino principal, se necesita crear un commit que fusione el último commit de la rama con el último commit del otro camino generado desde **main**.

Ambos casos son una fusión. La única diferencia es que en uno se genera un commit explícito y en el otro no, ya que el fast-forward no necesita uno.

## Eliminar ramas ¿Por qué?
Porque es una buena práctica. Además, las ramas tienen un propósito específico, lo que implica un corto período de vida. Así mantenemos limpio nuestro repositorio.

Para eliminar ramas se utiliza el comando:
* `git branch --delete <nombre_rama_a_eliminar>`

O, para resumir:
* `git branch -d <nombre_rama_a_eliminar>`

![imagen_rama_eliminada](imagenes/rama_eliminada.png)

En el caso de no haber fusionado la rama, nos aparecerá un mensaje de advertencia como el siguiente:

![imagen_rama_sin_fusionar](imagenes/rama_sin_fusionar.png)

Si quisiéramos eliminar la rama sin importar si esta se fusionó o no, tenemos que utilizar el siguiente comando:
* `git branch -D <nombre_rama_a_eliminar>`

Este comando nos permite borrar la rama sin necesidad de que haya sido fusionada.

![imagen_eliminada_-D](imagenes/rama_eliminada_-D.png)

Y como podemos apreciar la rama se elimina sin advertirnos que no fue fusionada.

