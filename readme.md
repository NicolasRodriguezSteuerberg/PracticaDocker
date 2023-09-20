## Práctica Docker

1. **Descarga la imagen ubuntu y comprueba que está en tu equipo.**
    1. `docker run ubuntu` *De esta manera si no encuentra la imagen localmente procederá a descargar la imagen*
    2. `docker image ls -a` *Este comando nos permite ver las imágenes que tenemos descargadas. Te debería salir algo parecido a esto:*
   
    |REPOSITORY|TAG|IMAGE ID|CREATED|SIZE|
    |------|------|------|------|------|
    |ubuntu|latest|c6b84b685f35|4 weeks ago|7.8MB|

<br>

2. **Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre**
    1. `docker run ubuntu`
    2. `docker ps -a` *Con este comando miramos todos los contenedores que tenemos, con el comando anterior lo abremos creado pero estará en modo cerrado. El primero que te saldrá sea posiblemente el último contenedor que hayas creado. En mi caso mi contenedor se creó con el nombre: **_vibrant_robinson_**. Vas al apartado names y miras su nombre. Te saldrá algo parecido a esto:*

    |CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES|
    |------|------|------|------|------|------|------|
    |3bf6b126e984|ubuntu|"/bin/bash" |8 minutes ago|Exited (0) 8 minutes ago||vibrant_robinson|
<br>

3. <a name="enlace1"></a>**Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?**
    1. `docker run -it --name dam_ubu1 ubuntu` *Gracias a esto crearemos el contenedor con el nombre **_dam_ubu1_**, para acceder al contenedor nada más crearlo podremos hacerlo agregando la variable -it, esto nos permite interactuar con el*

<br>

4. **Comprueba que ip tiene y si puedes hacer un ping a google.com**
    1. Para comprobar la ip necesitaremos descargar el net-tools en el contenedor:
        1. ` apt update` *Actualiza la lista de paquetes*
        2. `apt install net-tools` *Descargamos el paquete de net-tools*
        3. Finalmente para ver la ip utilizamos el comando: `ifconfig`
    2. <a name="enlace2"></a>Para poder ver si podemos hacer ping a google.com por ejemplo primero tendremos que instalar su debido paquete:
        1. `apt install iputils-ping` *Descarga el paquete que nos permite hacer ping*
        2. Para hacer ping usaremos el comando `ping google.com`, de esta manera hacemos ping con google, para parar el ping le daremos al Ctrl + C

<br>

5. **Crea un contenedor con el nombre 'dam_ubu2'. ¿Puedes hacer ping entre los contenedores?**
    1. Para crear el contenedor haremos como en uno de los apartados anteriores pero con el nombre **_dam_ubu2_**: [aquí](#enlace1)
    2. Para hacer ping instalaremos en este ultimo el ping como en el apartado anterior: [aqui](#enlace2)
        1. Ahora que lo tenemos hacemos el comando `ping 172.17.0.2`, el 172.17.0.2 es la ip que tengas en el otro contenedor.
    

6. **Sal del terminal, ¿que ocurrió con el contenedor?**
    
    Al cerrar la terminal el contenedor no se cierra, sigue activo. ¿Como sabemos esto? Pues abriendo una nueva terminal y poniendo el comando `docker ps`, con este comando vemos los contenedores que estan activos. Se veria algo parecido a esto:

    |CONTAINER ID|IMAGE|COMMAND|CREATED|STATUS|PORTS|NAMES|
    |------|------|------|------|------|------|------|
    |3dfdd64d085b|ubuntu|"/bin/bash" |21 hours ago|Up 2 minutes||dam_ubu2|

<br>

7. **¿Cuanta memoria en el disco duro ocupaste?**

    >Para ver la memoria que ocupa docker cuenta con un comando que nos facilita ver esto. Este comando nos permite ver las imagenes, los contenedores (esto de forma general). Para que esto sea más específico usamos la variable "_-v_", quedando el comando de esta forma `docker system df -v`.<br>
    En mi caso el contenedor dam_ubu1 pesa 46.1MB, mientras que dam_ubu2 pesa 45.6<br>
    El resultado del comando se verá algo como esto:
    
    |CONTAINER ID|IMAGE|COMMAND|LOCAL VOLUMES|SIZE|CREATED|STATUS|NAMES|
    |------|------|------|------|------|------|------|------|
    |3dfdd64d085b|ubuntu|"/bin/bash" |0|45.6|21 hours ago|Up 7 minutes |dam_ubu2|
    |8c70124f0e48|ubuntu|"/bin/bash" |0|46.1|22 hours ago|Exited (137) 21 hours ago|dam_ubu1|

8. **¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?**



<details><summary>Aqui os dejo un enlace a un repositorio donde tengo más apuntes sobre docker</summary>

[Mis apuntes](https://github.com/NicolasRodriguezSteuerberg/CosasPc/tree/main/2/Apuntes/SXE)
</details>