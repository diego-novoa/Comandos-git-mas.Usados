#comandos utiles de git

1. git init = inicializar la tarea
2. git add . = toma la inicialicacion de tareas y los prepara para la fotografia despues de inicializar
3. git reset . = reseteo la tarea anterior si me doy cuenta que falta informacion
4. git commit -m = prepara los archivos para la foto
5. git checkout -- . = restaura la informacion del repositorio que le estamos asiendo seguimiento.
6. git log = me muestra todo el listado de los commit que se han realizado [para salir del comando git log ] [presiono la letra[q]].
7. git commit --amend = sirve para arreglar el mensaje del (commit), estando dentro del comando doy click a la letra(i) para cambiar el mensaje (para salir del comando doy clik al (ctrl + c (luego escribo (qw! y presiono enter)))).
8. git checkout -b ejemplo-rama = (Switched to a new branch 'ejemplo-rama'),Git creó una nueva rama llamada ejemplo-rama (Y automáticamente cambió a esa rama)
9. git checkout master = (significa cambiarte a la rama master en tu repositorio Git.)
10. git merge ejemplo-rama = (significa que quieres combinar los cambios de la rama ejemplo-rama dentro de la rama en la que estás actualmente.)
11. git branch -d ejemplo-rama =(significa que quieres eliminar la rama local llamada ejemplo-rama.)  
12. git push = 
13. git branch = 
14. git push origin master = si te aparece un mensaje [On branch master nothing to commit, working tree clean] resuelvo con [git push origin master].
- [cuando aparezca,[The most similar command is commit]] es por escribir mal el comando [commit].
- (Please make sure you have the correct access rights and the repository exists.), significa que Git no puede acceder al repositorio remoto. Normalmente aparece cuando haces: git push
- Already up to date.(aparece cuando ejecutas un comando como:git pull), y significa que no hay cambios nuevos que traer o combinar.
- (que significa, error: cannot delete branch 'ejemplo-rama' used by worktree at 'C:/Users/diego/OneDrive/Desktop/proyectos Diego Novoa'), Cómo solucionarlo,(Cambiar a otra rama (por ejemplo, git checkout master
ter): despues de ejecutar este comando se ejecuta (git branch -d ejemplo-rama))

git remote set-url origin <https://github.com/diego-novoa/Comandos-git-mas.Usados.git>

