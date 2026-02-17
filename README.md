### comandos git

- git init
- git add .
- git reset .
- git commit -m
- git checkout -- .
- git log
- git commit --amend
- git checkout -b 
- git checkout master
- git merge ejemplo-rama
- git branch -d ejemplo-rama
- git push
- git branch
- git push origin master
- git checkout ejemplo-rama

# git init: es un comando de Git que sirve para crear un nuevo repositorio Git en una carpeta de tu computadora.
# git add . : es un comando de Git que sirve para preparar todos los cambios del directorio actual para el próximo commit.
# git reset . : es un comando de Git que se usa para quitar archivos del área de preparación (staging area) sin borrar los cambios que hiciste en el código.
# git commit -m : Este comando crea un nuevo "commit" en Git, que es como una instantánea de los archivos en su estado actual. Antes de hacer un commit, normalmente: Has agregado cambios al área de staging con git add. O bien quieres incluir cambios ya preparados en el commit.
# git checkout -- . : restaura todos los archivos modificados en tu directorio de trabajo al estado del último commit en la rama actual.
# git log : es un comando de Git que te permite ver el historial de commits de un repositorio. Es como mirar una “línea de tiempo” de todos los cambios que se han hecho en tu proyecto. Cada commit representa un conjunto de cambios guardados, y git log te muestra información importante sobre ellos.
# git commit --amend : en Git se utiliza para modificar el último commit realizado. En lugar de crear un nuevo commit, reemplaza el commit más reciente por uno nuevo que incluya los cambios que desees. Es muy útil para corregir errores pequeños, como un mensaje de commit mal escrito o archivos olvidados.
# git checkout -b : en Git se usa para crear y cambiar a una nueva rama en un solo paso. Veamos esto paso a paso:
# git checkout master : es un comando de Git, el sistema de control de versiones, que sirve para cambiar de rama en un repositorio.
# git merge: es un comando de Git que se utiliza para combinar el historial de dos ramas en una sola. Básicamente, toma los cambios de una rama y los integra en la rama en la que te encuentras actualmente. Es una forma de unir el trabajo de diferentes desarrolladores o diferentes líneas de desarrollo dentro de un mismo repositorio.
# git branch -d : se utiliza en Git para eliminar una rama local de tu repositorio, pero con una condición: solo eliminará la rama si ya ha sido fusionada con la rama actual o con la rama base (normalmente main o master). Esto evita perder cambios que no se han guardado en otra rama.
# git push : es un comando de Git, el sistema de control de versiones, que se utiliza para subir los cambios locales de tu repositorio a un repositorio remoto (por ejemplo, en GitHub, GitLab o Bitbucket). Básicamente, es la manera de compartir tu trabajo con otros o de respaldarlo en la nube.
# git branch : es un comando de Git que se usa para crear, listar, renombrar o eliminar ramas (branches) dentro de un repositorio.
# git push origin: es un comando de Git que se usa para enviar (subir) tus cambios locales a un repositorio remoto.
# git checkout : es un comando de Git que se usa para cambiar de rama o restaurar archivos a una versión anterior.




