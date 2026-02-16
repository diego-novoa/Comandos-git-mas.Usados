### comandos git

- git init
- git add .
- git reset .
- git commit -m
- git checkout -- .
- git log
- git commit --amend
- git checkout -b ejemplo-rama
- git checkout master
- git merge ejemplo-rama
- git branch -d ejemplo-rama
- git push
- git branch
- git push origin master
- git checkout ejemplo-rama

> git init es un comando de Git que sirve para crear un nuevo repositorio Git en una carpeta de tu computadora.

```flow
st=>start: Login
op=>operation: Login operation
cond=>condition: Successful Yes or No?
e=>end: To admin

st->op->cond
cond(yes)->e
cond(no)->op
```


