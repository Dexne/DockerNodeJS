# Creación de microservicio con docker y Node JS
**By: Dexne**

En este repositorio presentamos una implementación simple de cómo desplegar un microservicio ( un generador de contraseñas ) con ayuda de Docker y el framework Node.Js.

¿Qué es Docker?

Docker es una plataforma de virtualización ligera que simplifica el despliegue y la gestión de aplicaciones en entornos aislados llamados contenedores. Permite empaquetar, distribuir y ejecutar aplicaciones con consistencia independientemente del entorno.

¿Cómo funciona?

Docker opera mediante la creación de contenedores, envases virtuales aislados que encapsulan aplicaciones y dependencias, compartiendo el mismo sistema operativo subyacente para una ejecución eficiente, portátil y consistente en diferentes entornos de desarrollo, pruebas y producción.

El presente código sigue una estrucuta básica de un proyecto de Node.JS y express para apoyarnos del backend, además, se especifica dentro del dockerfile que se esta haciendo uso de node 12.22.1- alpine3.11, una versióin bastante ligera y estable.

El proyecto es sensillo, se levanta un host local en primera instancia que esta conectado a unos archivos js, los cuales nos permiten visuaizar el contenido de los json, arhivos que son usados para imprimir o mostrar los datos del microservicio.
Para ello, se utiliza funciones random para generar caracteres de un arreglo de posibles candidatos a formar estas contraseñas. Finalmene se hace uso de docker para encapsularlo en contenedores para poder ser compartido sin importar las versiones nuevas o viejas que puedan existir.

A continación adjunto imagenes del proceso:

En un inicio se levantó el host local pero como no estaban definidas rutas no era posible mostrar nada.

![SinRouteo](https://github.com/Dexne/DockerNodeJS/blob/main/assets/SinRouteo.jpeg)

Debería de observarse de esta manera:

![Ejecución](https://github.com/Dexne/DockerNodeJS/blob/main/assets/Ejecucion_Docker.jpeg)

Construimos la imagen:

![construccion de imagen](https://github.com/Dexne/DockerNodeJS/blob/main/assets/construccionDeImagen.jpeg)

Verificamos en Docker Desktop que se halla creado:

![Verificacion Docker Desktop](https://github.com/Dexne/DockerNodeJS/blob/main/assets/verificacionEnDockerDesktop.jpeg)

También podemos hacer esto desde la terminal:

![Verificacion en terminal](https://github.com/Dexne/DockerNodeJS/blob/main/assets/verificacionEnterminal.jpeg)

Con ayuda del comando:

```
docker run --name"AgregamosUnNombre" -p 4000:3000 "imagen"
```

Y lo desplegamos ahora con nombre, cabe mencionar que el primer puerto es el puerto externo, el que podremos usar desde el navegador del dispositivo, el segundo puerto es usado por docker en sus contenedores.

![Puertos](https://github.com/Dexne/DockerNodeJS/blob/main/assets/puertoExternoInterno.jpeg)

Comprobamos desde Docker Desktop que se estan usando:

![Comprobacion1](https://github.com/Dexne/DockerNodeJS/blob/main/assets/UsuarioDocker.jpeg)

![Comprobacion2](https://github.com/Dexne/DockerNodeJS/blob/main/assets/extra.jpeg)
