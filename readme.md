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

3. **Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?**
    1. `docker run -it --name dam_ubu1 ubuntu` *Gracias a esto crearemos el contenedor con el nombre **_dam_ubu1_**, para acceder al contenedor nada más crearlo podremos hacerlo agregando la variable -it, esto nos permite interactuar con el*

<br>

4. **Comprueba que ip tiene y si puedes hacer un ping a google.com**


5. **Crea un contenedor con el nombre 'dam_ubu2'. ¿Puedes hacer ping entre los contenedores?**

6. **Sal del terminal, ¿que ocurrió con el contenedor?**

7. **¿Cuanta memoria en el disco duro ocupaste?**

8. **¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?**



<details><summary>Aqui os dejo un enlace a un repositorio donde tengo más apuntes sobre docker</summary>
![Mis apuntes](https://github.com/NicolasRodriguezSteuerberg/CosasPc/tree/main/2/Apuntes/SXE)
</details>