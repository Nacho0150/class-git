# CLASE 1 MIÉRCOLES 27 DE MARZO DEL 2024

>Lo que vimos en la clase anterior:

<sub>
Abrimos la terminal de Git Bash en Window o la terminal de Ubuntu, tambien la terminal de Mac, y comenzamos con los siguientes comandos y creación de directorios
</sub>

```sh
pwd  #Vemos la ruta de la carpeta en la que estamos
cd #Es para navegar a una carpeta: change directory -> cambiar de directorio
cd / #Nos llava al home, en la raíz del disco
cd ~ #La virgulilla significa que estamos en el lugar de los documentos o del usuario
ls #Esto es listar los archivos, nos muestra todos los archivos en la raíz
ls -al #El espacio -al significa que es un argumento especial para ver archivos ocultos
#Usar la flecha hacía arriba nos muestra el último comando utilizado
ls -l #Muestra casi todos los archivos sin los que están ocultos
ls -a #Muestra el grupo de archivos pero no en una lista
clear #Limpia la consola o ctrl + l
cd .. #Nos devuelve a la carpeta anterior
cd U + tab #Esto se usa para un autocompletado o para buscar una referencia
cd /D #Cambiamos de disco en window
df -h #Muestra todos los directorios en Ubuntu
cd /mnt/d #Cambia de directorio usando WSL Ubuntu en window
```


## AHORA COMENZAMOS CON LA CREACIÓN DE CARPETAS

```sh
cd ..
cd ..
cd /mnt/c
cd ~ #Vamos a la raíz
mkdir Tecnicatura #Recordar que en window las mayúsculas no tienen relevancia, pero si en Linux
cd tecnicatura
mkdir Python
mkdir Java
mkdir JavaScript
```
<sub>
Revisar y ejecutar cada comando, hacerlo como practica
</sub>
<sub>
Profesor Ariel Betancud
</sub>


# CLASE 4 MIÉRCOLES 17 DE ABRIL DEL 2024

>Analizar cambios en los archivos de tu proyecto Git parte 4

<sub>
Ingresamos de la siguiente manera:
</sub>

<sub>
Abrir git bash en Window o la terminal de Linux o de Mac: al abrir Git Bash hacerlo como administrador, en terminal también o usar sudo para permisos especiales.
</sub>

<sub>
TAREA -> AGREGAR LOS COMENTARIOS EN LOS COMANDOS, PARA SABER QUE PASA CON CADA UNO.
</sub>

```sh
cd tecnicatura
cd class-git
ls
touch historia.txt
code .
#Modificamos el archivo historia.txt colocando lo siguiente: Bienvenido     mi nombre es Ariel (coloca tu nombre)
ctrl + s
git status
git add .
git status
git commit #Sin agregar -m veremos que pasa
#Agregar mensaje y salir con
Esc #Presionamos Escape 
:wq! + enter #Y ya salimos si estamos en git bash con window
Esc + shift + z + z #Salimos del mensaje para el commit, en linux, esto anda en algunas terminales
#Agregamos otra línea de mensaje en historia.txt desde VSC: estoy estudiando programación
ctrl + s
git add .
git commit
#Se abre un editor de código basado en línea de comandos, editor de texto como VSC llamado vim
Esc + i #Para comenzar a escribir mensaje del commit, no suele ser necesario
ctrl + x #Para salir en linux
s + enter #Para decir si al cambio y aceptar el nombre, ósea no cambiamos el nombre, la (s) es de si y la (y) es de yes, no olvidar enter en linux
git show #Vemos todos los cambios en el último commit
git log historia.txt #Vemos todos los commit
q #Para salir del registro de commits
#Copiamos un hash mas antoguo y otro reciente, ingresamos el siguiente comando
git diff hash_commit_numerico hash_commit_numerico #Comparamos diferentes commits y sus cambios, poner la versión mas vieja primero, luego la mas nueva
q #Para salir
cd ..
cd ..
```

# CLASE 5 MIÉRCOLES 8 DE MAYO DEL 2024


>Volver en el tiempo en nuestro repositorio utilizando reset y checkout parte 6

<sub>
Ingresamos de la siguiente manera:
</sub>

<sub>
Abrir git bash en Window o la terminal de Linux o de Mac: al abrir Git Bash hacerlo como administrador, en terminal también o usar sudo para permisos especiales.
</sub>

<sub>
TAREA -> AGREGAR LOS COMENTARIOS EN LOS COMANDOS, PARA SABER QUE PASA CON CADA UNO.
</sub>

```sh
cd tecnicatura
cd class-git
ls
code .
git log #Vemos los commit hechos hasta ahora
Copiar el hash #El número largo que tiene el commit
git reset hash-nombre-commit #Este nos permite volver a una versión anterior, hay 2 tipos de reset: el duro y el suave
git status
git add .
git commit -m "Agregamos datos de estudios en historia.txt"
git config --list #Veremos la configuración que ya hemos hecho con en nombre y email
git reset hash-nombre-commit --hard #Es el duro, todo vuelve a su estado anterior, es el más usado, desaparece todo
git reset hash-nombre-commit --soft #Este es el suave, lo que tengamos en staging segirá allí
crear un archivo #portafolio.html introducir el código y
touch portafolio.html
html : 5 #Con esto se carga el código básico de html y modificamos
ctrl + s #Guardamos
Clic derecho en VSC Open with Live Server para ver en el navegador
git status
ls
ls -al
git add .
git status
git commit -m "Agregamos el html para nuestro portafolio"
creamos CSS #Este es un archivo de estilos, para esto creamos una nueva carpeta llamada css
mkdir css
ls
cd css
touch style.css #creamos un archivo dentro: estilos.css le cargamos el código.
ctrl + s #abrimos en el navegador y todo esta allí, pero todo esto supuestamente en git no existe.
git status #tenemos cosas en el área de trabajo, en staging distintas
git diff + enter #y nos muestra los cambios en memoria ram y en disco
git add . #Agregamos todo al staging
git status #Ya esta todo en memoria ram, a git solo le importan los archivos, guarda las carpetas como rutas y automaticamente las crea
git commit -m "Creamos el css para darle algo de estilo a nuestro portafolio"
git log #vemos lo nuevo que hemos hecho sin lo que borramos con el reset fuerte
hacer cambios en historia.txt #Cambiamos la última línea y
ctrl + s 
git diff
git commit -am "cambio en la última línea del historia.txt"
git log
q  #Esto para salir
git log --stat #veremos los cambios especificos que hicimos en cuales archivos por medio del commit y veremos los cambios en bits
q #salimos de la línea de commits, ahora queremos ver como era originalmente el archivo, osea la primera versión, copiamos el nombre del primer commit
git checkout hash-nombre-commit historia.txt #Veremos el archivo en su estado original
git status #Nos sugiere hacer un commit, si lo hacemos borramos todo lo que hicimos antes, debemos seguir con el siguiente commando
git checkout master historia.txt #Volvemos a la versión master del archivo historia.txt, esto es muy peligroso
git checkout hash-nombre-commit historia.txt #Volvemos a hacer esto y cambiamos cosas del archivo
git commit -am "Reemplazo de una versión por otra de la historia"
git log #Veremos los cambios sin tocar ningun otro archivo, esta es la forma de volver a una versión hacía atrás y llevarla a la cabeza de la master
cd ..
cd ..
```