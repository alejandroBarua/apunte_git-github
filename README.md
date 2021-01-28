<div align="center">
  <h1> Git & Github </h1>
 
  <sub>Autor:
  <a href="#" target="_blank">Alejandro Barua</a><br>
  </sub>
</div>

### Como empezar a trabajar con Git

[instalar git](https://git-scm.com/downloads)

Para trabajar con git se usa la terminal, comandos utiles:

```sh
$ ls
muestra los archivos de la carpeta donde estoy
```

```sh
$ cd nombre_carpeta
ingreso a la carpeta
```

```sh
$ cd ..
vuelve a la carpeta anterior
```

Estos comandos nos ayudaran a ir a la carpeta de nuestro proyecto. Una ves alli:

```sh
$ clear
limpia la terminal
```

```sh
$ git init
crea un repositorio local y una rama master
```

Si es es la primera ves que usas git debes configurar tu asuario y email:

```sh
$ git config --global user.name "nombre"
```

```sh
$ git config --global user.email "email"
```

```sh
$ git config --list
para verificar los cambios
```

Ya podemos empezar a programar!

```sh
$ code
abre tu editor de texto por defecto, el mio.. vs code
```

### Como agregar un commit al repositorio

Cada cambio guardado en el repositorio se llama commit.
Supongamos que terminamos de hacer una tarea y queremos guardar los cambios en el repositorio:

```sh
$ git status
nos dice si se realizo algun cambio que podemos guardar, verifica si los cambios se agregaron al staging area
```

```sh
$ git add .
antes de hacer un commit hay que agregar todos los archivos modificados al staging area
```

```sh
$ git commit -m "descripcion del cambio realizado"
guardo el commit
```

```sh
$ git commit -am "descripcion del cambio realizado"
es el atajo para pasar al staging area y hacer el commit
```

```sh
$ git log
lista de todos los commits (si hay muchos commits salimos con la letra q)
```

```sh
$ git log -oneline
lista los commits de forma resumida
```

```sh
$ git log -S "palabra"
lista los commits que lleven la "palabra"
```

### Como volver atras a un commit especifico

Cada commit tiene un id asociado por ejemplo: commit 15f62cd6bc6dad407a93ccbd0f7a585770052fe5, o podemos usar la forma resumida 15f62cd

```sh
$ git checkout id_commit
vuelve al commit elejido sin borrar los ultimos commits, se usa si queremos ver como estaban
nuestros archivos antes, de la misma forma podemos volver al ultimo commit
```

```sh
$ git restore
vuelve al ultimo commit que guarde, osea que borrar los cambios que realize despues del ultimo
commit.
```

```sh
$ git reset id_commit --hard
vuelve al commit elejido y borra todos los commits que estaban despues de este
```

### Manejo de ramas en git

Por defecto empezamos a trabajar en la rama master.
Cada rama va a tener sus propios commits y en cada una se trabaja de manera independiente.

```sh
$ git branch nombre_rama
crea una nueva rama con el progreso de la rama en la que estaba
```

```sh
$ git branch --list
muestra una lista de todas las ramas y en que rama me encuentro
```

```sh
$ git checkout nombre_rama
cambiamos de rama
```

**No se recomienda trabajar con la rama master (se la llama ambiente de produccion). Creamos una rama secundaria, por ejemplo, para la creación de una funcionalidad que queramos integrar en un programa y para la cual no queremos que la rama principal se vea afectada**

Luego para pasar los cambios de la rama secunadaria con nuestra nueva funcionalidad, a la rama master:

```sh
$ git checkout master
primero debemos estar en la rama que va a absorber a la otra
```

```sh
$ git merge rama_secunadaria -m "mensaje/descripcion"
master absorbera a la rama secundaria
```

```sh
$ git branch -D nombre_rama
borra la rama
```
