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
Git es una herramient de control de versiones diseñado por Linus Torvalds.
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