# Práctica del curso de git, GitHub y Source Tree
**Óscar Antón Galante**
 
\#IV Bootcamp Web

Diciembre 2017


## Preguntas

### ¿Qué comando utilizaste en el paso 11? ¿Por qué?

```git
git reset --hard HEAD~1
```
Retrocedí mediante el comando ```reset``` un paso en el HEAD usando ```HEAD~1``` y apliqué el modificador ```--hard``` para que los cambios también se reflejasen en el *Working Copy*.

### ¿Qué comando utilizaste en el paso 12? ¿Por qué?

Mediante el comando ```git reflog``` busco el *HASH* del commit anterior a mi último paso.

Aplico posteriormente el mismo comando ```git reset --hard 166a9a5``` (dónde 166a9a5 es el *HASH* del commit previo al paso 11) para retroceder a dicha posición y anular el movimiento del paso 11 aplicando también los cambios en el *Working Copy*.

### El merge del paso 13, ¿causó algún conflicto? ¿Por qué?

Al realizar el ```git merge master``` desde la rama **styled** nos da como respuesta ```Already up to date```.

Al estar en la misma línea y tener **styled** una posición más avanzada que **master** entiendo que debería ser esta última la que hiciese un ```git merge styled``` una vez que nos hubiesemos situado sobre ella.

### El merge del paso 19, ¿causó algún conflicto? ¿Por qué?

Accedo a la rama **styled** con ```git checkout styled``` y procedo a ejecutar el comando ```git merge htmlify```.

Han entrado en conflicto dos *commits* y da como resultado ```Merge conflict in git-nuestro.md```.

Por un lado está el archivo ```git-nuestro.md``` con los estilismos de la rama **styled** y por otra parte esta el mismo archivo con las modificaciones y tags HTML de la rama **htmlify**.

Antes de poder proceder a realizar el *merge* tengo que resolver el conflicto de versiones.

Me quedo con la versión **styled** y procedo a realizar un ```git add git-nuestro.md``` y posteriormente un ```git commit``` antes de finalmente realizar un ```git merge htmlify``` desde la rama **styled** a la que había llegado mediante ```git checkout styled``` al principio del proceso.

### El merge del paso 21, ¿causó algún conflicto? ¿Por qué?

El merge ```git merge styled``` desde **master** no ha causado ningún conflicto y se han incorporado las modificaciones en ```git-nuestro.md``` de la rama **styled** mediante *fast forward*.

Se ha posicionado el *HEAD* en **style** y **master**.

### ¿Qué comando o comandos utilizaste en el paso 25?

Para dibujar el diagrama he empleado el comando ```git log --graph --decorate --pretty=oneline```.

### El merge del paso 26, ¿podría ser *fast forward*? ¿Por qué?

Si que se podría haber hecho un *merge fast forward* ya que ambas ramas, **master** y **title**, estaban en la misma línea y no era necesario crear un nuevo *commit* (como el que se ha creado con el comando ```--no-ff```, utilizado al realizar el *merge no fast forward*) que tuviese a ambas como *parent*.

### ¿Qué comando o comandos utilizaste en el paso 27?

Como justo solo tengo que deshacer el merge del paso anterior realizo un ```git reset HEAD~1``` sin emplear el comando ```--hard``` para que no me modifique mi *working copy*.

### ¿Qué comando o comandos utilizaste en el paso 28?

Empleo ```git reflog``` para localizar el commit en el que introduje las modificaciones al título del archivo, selecciono el anterior a ese.

Mediante el comando ```git reset --hard f3dafe4``` (siendo ```f3dafe4``` el *HASH* previo a la eliminación del *merge*) vuelvo a la situación inicial.

### ¿Qué comando o comandos utilizaste en el paso 29?

```git branch -D title```

### ¿Qué comando o comandos utilizaste en el paso 30?

Con ```git reflog```vuelvo a localizar la posición del *hash* relativo al *merge* realizado, en este caso es ```2177979```.

Aplico el comando ```git reset --hard 2177979``` y vuelvo a la misma situación que tenía al finalizar el paso 26.

### ¿Qué comando o comandos utilizaste en el paso 32?

Con ```git reflog```vuelvo a localizar la posición del *hash* relativo al inicio del poema, en este caso es ```ba1cd61```.

Aplico el comando ```git reset --hard ba1cd61``` y vuelvo a la misma situación que tenía al hacer el commit de la primera redacción del poema.

### ¿Qué comando o comandos utilizaste en el paso 33?

Con ```git reflog```vuelvo a localizar la posición del *hash* relativo al punto de introducción del título tras el *merge* con la rama **title**, en este caso es ```2177979```.

Aplico el comando ```git reset --hard 2177979```

