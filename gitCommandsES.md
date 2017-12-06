# Guía de conmados para el uso de GIT

## Comándos básicos

Comando | Resultado
------- | ---------
`git init` | Inicializamos repositorio git en el directorio actual
`git status` | Obtenemos en pantalla el estado del repositorio
`git add <element>` | Añadimo `<element>` al **staging area**
`git commit` | Añadimos el contenido del **staging area** al repositorio
`git commit -m "message"` | Añadimos el contenido del **staging area** al repositorio, pasando además, mensaje descriptivo del contenido
`git rm <element>` | En un sólo paso, borra `<lement>` y lo añade al **staging area**
`git diff` | Muestra las diferencias entre el **working copy** y el **staging area**
`git diff --staged` | Muestra las diferencias entre el **staging area** y el **repo**
`git diff HEAD` | Muestra las diferencias entre el **working copy** y el **repo**
`git reset HEAD~1` | Desace el último **commit** manteniendo el estado actual del **working copy**
`git reset --hard HEAD~1` | Desace el último **commit** devolviedo el **working copy** a su estado anterior, perdiéndose los cambios que se hayan podido realizar
`git reset HEAD <element>` | Saca `<element>` del **staging area** y lo devuelve al **working copy**
`git show` | Muestra la información de un **commit**
`git tag` | Devuelve un listado de las etiquetas del **repo**
`git tag <tag>` | Crea una etiqueta `<tag>` en el lugar donde se ubica el puntero **HEAD**
`git tag -d <tag>` | Elimina la etqieta `<tag>`
`git log` | Log de los **commits** realizados hasta el momento
`git log --graph` | Muestra el log de los **commits** realizados en formato gráfico
`git log --decorate` | Muestra el log de los **commits** realizados con los punteros
`git log --pretty=onelene` | Muestra el log de los **commits** realizados resumidos en una sola línea
`git reflog` | Muestra todo lo que ha pasado en nuestro **repo**
`HEAD~n` | Modificador para situar el puntero en el **commit** n inferior al actual
`HEAD@{n}` | Modificador para situar el puntero en punto n infoerior del **reflog**. No tiene por qué coinididr con `HEAD~n`.

## Ramas

Comando | Resultado
------- | ---------
`git branch` | Muestra las ramas exostentes en el grafo del **repo**
`git branch <branchName>` | Crea la rama `<branchName>` en la posición actuál del puntero
`git ckeckout <branch>` | Cambia el puntero **HEAD** a la rama `<branch>`. El contenido del **working copy** varia
`git branch -m <branchName> <newBranchName>` | Cambie el nombre de la rama `<branchName>` por `<newBranchName>`
`git branch -D <branchName>` | Eliminanos la rama `<branchName>`. El contenido del **working copy** y el **staging area** no varia
`git merge <branch>` | La rama en la que estamos absorve a la rama `<branch>` con **fast-forward** (sin **commit** intermedio)
`git merge --no--ff <branch>` | La rama en la que estamos absorve a la rama `<branch>` sin **fast-forward** (con **commit** intermedio)

## Repositorio remotos

Comando | Resultado
------- | ---------
`git remote` | Muestra los repositorios remotos que hay en nuestro **repo** local
`git clone <url>` | Crea una carpeta en el directorio actual con el mismo nombre del **repo** remoto y descarga todo su contenido
`git remote add <remoteName> <url>` | Añade `<remoteNmae>` como **repo** remoto
`git push <remoteName> <branch>` | Sube los cambios de nuestro repositorio local al remoto en la rama indicada
`git fetch <remoteName>` | Descarga todos los cambios en todas las ramas de `<remoteName>` desde la última vez que descargamos
`git fetch <remoteName> <branchName>` | Descarga todos los cambios en `<branchName>` en `<remoteName>` desde la última vez que descargamos
`git pull <remoteName>` | Descarga y aplica los cambios del repositorio remoto. Hace `git fetch` y `git merge` a la vez
`git push <remoteName> --delete <branchName>` | Borra una rama del **repo** remoto