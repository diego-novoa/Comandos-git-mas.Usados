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

git remote set-url origin https://github.com/diego-novoa/Comandos-git-mas.Usados.git

ejercicio practico con la rama (ejemplo-rama a master)

- El comando git branch se utiliza para ver y gestionar las ramas de tu repositorio Git. Te explico detalladamente:
Lista todas las ramas locales de tu repositorio.

- La rama en la que estás actualmente aparece con un asterisco *.
Ejemplo de salida:
* master
  develop
  feature-login

- Ver ramas remotas: con, [git branch -r]

Esto solo crea la rama pero no cambia a ella. Para moverte, usa: [git checkout nombre-rama]
O la forma combinada más moderna: [git switch -c nombre-rama]

Cambiar de rama: [ git checkout nombre-rama
                    # o con Git moderno
                   git switch nombre-rama]

- actualizar ejemplo-rama a master:

# 1. Cambia a tu rama
git checkout ejemplo-rama

# 2. Trae los últimos cambios del repositorio remoto
git fetch origin

# 3. Fusiona master en tu rama
git merge origin/master


: Si hay conflictos, Git te pedirá resolverlos.:aparece[Already up to date.], esta actualizado.

Después de resolverlos, haz: git add .
                             git commit

- haz: git add . [despues de darle,  git add . , me aparecio esto, hint: You've added another git repository inside your current repository. 
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint:
hint:   git submodule add <url> Practicas-JavaScript-React-Native
hint:
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint:
hint:   git rm --cached Practicas-JavaScript-React-Native
hint:
hint: See "git help submodule" for more information.
hint: Disable this message with "git config set advice.addEmbeddedRepo false"]

Ah, esto explica lo que está pasando: Git detectó que dentro de tu repositorio actual estás intentando agregar otro repositorio Git (Practicas-JavaScript-React-Native). Eso se llama un repositorio anidado, y Git no lo permite directamente porque los clones del repositorio principal no traerían ese repositorio interno.

Por eso te aparece este mensaje de hint. Tienes dos opciones según lo que querías hacer:

# Elimina la carpeta del index si ya la agregaste
git rm --cached Practicas-JavaScript-React-Native

# Agrega como submódulo apuntando al URL del repositorio original
git submodule add <URL_DEL_REPO> Practicas-JavaScript-React-Native


aplique [git rm --cached Practicas-JavaScript-React-Native] apareció [error: the following file has staged content different from both the
file and the HEAD:
    Practicas-JavaScript-React-Native
(use -f to force removal)]

Git intentó remover el archivo del índice (staging area) sin borrarlo de tu disco. Pero el error que te dio dice:[error: the following file has staged content different from both the file and the HEAD]

Eso significa que:

El archivo ha sido modificado y está en staging (index).
Los cambios en staging son diferentes tanto del archivo en tu disco como del último commit (HEAD).
Por seguridad, Git no quiere removerlo del índice porque se perderían esos cambios que están staged.
Por eso te sugiere usar:[git rm --cached -f Practicas-JavaScript-React-Native]

El -f forzará la eliminación del archivo del staging, pero no tocará el archivo en tu disco. Después de eso, el archivo seguirá en tu carpeta local pero ya no estará en Git.

💡 Tip extra: Si tu intención era ignorar ese archivo en futuros commits, asegúrate de agregarlo al .gitignore después de removerlo del índice:

echo "Practicas-JavaScript-React-Native" >> .gitignore
git add .gitignore
git commit -m "Ignorar Practicas-JavaScript-React-Native"

. Verificar que Git ya lo está ignorando: [git status]
-Deberías ver que Practicas-JavaScript-React-Native ya no aparece como archivo staged ni como cambio pendiente. Esto confirma que Git lo ignorará en futuros commits.
. Subir los cambios al repositorio remoto:[git push origin ejemplo-rama] Esto actualizará el repositorio con:
El commit que ignora el archivo, La eliminación del archivo del control de versiones
. Comprobar: [.gitignore]

-.... no se dieron los cambios aparece todo igual: [Ah, ahora entiendo: hiciste todos los cambios en tu rama, que llamaste ejemplo-rama, pero al revisar master (o main) esos cambios no aparecen. Esto es completamente normal: Git no copia automáticamente los cambios de una rama a otra.
Para que los cambios que hiciste en ejemplo-rama aparezcan en master, tienes dos opciones principales:]
1... Hacer un merge de la rama a master: [git checkout master]
2...Trae los cambios de tu rama: [git merge ejemplo-rama]
suiente:[que significa, Updating bb6efa9..289ac31 Fast-forward .gitignore | Bin 311 -> 407 bytes 1 file changed, 0 insertions(+), 0 deletions(-)]: Git avanzó tu rama local hasta la versión más reciente de forma directa (fast-forward). Solo un archivo (.gitignore) cambió de tamaño, pero no se modificaron líneas de texto.
3...que sigue, para terminar de pasar los datos:[Verifica el estado actual de tu repositorio [git status]]
Esto te dirá si hay archivos pendientes de agregar (staged) o confirmar (commit).
Si todo está limpio, verás algo como:[On branch main
                                Your branch is up to date with 'origin/main'.
                                nothing to commit, working tree clean]

despues de git status, me aparecio esto, On branch master
Your branch is ahead of 'origin/master' by 17 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Practicas-JavaScript-React-Native/
nothing added to commit but untracked files present (use "git add" to track)

4... Estás en la rama master y tienes 17 commits locales que aún no has subido al repositorio remoto (origin).
👉 Para subirlos:[git push origin master]


# segundo ejercicio 
realice cambios en visual estudio code, pero no se reflejan en git. 
1.. aplico: [git add .]
2.. aplico: [git commit -m]
la respuesta es: On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean[No hay nada que "resolver". Git te está diciendo que:✔ No hiciste cambios
                                     ✔ No hay archivos nuevos
                                     ✔ Todo está actualizado]
3.. aplico: [git push origin main] me aparecio, Everything up-to-dat, significa que Git no encontró cambios nuevos en tu rama main que necesiten ser enviados al repositorio remoto (origin). En otras palabras, tu repositorio local y el remoto ya están sincronizados.
Algunas razones comunes para que esto ocurra:
1.. No has hecho commits nuevos, Revisa tus cambios con:[git status], aplique, git status y sigue sin subir los cambios en git
