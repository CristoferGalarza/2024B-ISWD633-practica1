# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

![srv-web](Seccion3/ContenedorNginx.png)
# COMPLETAR

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

![sin nombre](Seccion3/ContenedorSinNombre.png)

![sin nombre](Seccion3/MuestreContenedorSinNombre.png)
# COMPLETAR

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

![ejecutandose o no](Seccion3/ListarContenedoresEje.png)

![ejecutandose o no](Seccion3/ListarContenedoresEjeVisual.png)
### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

![iniciar srv-web](Seccion3/IniciarContenedorSrv.png)
# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```
![ejecutandose](Seccion3/ListarContenedoresEjecutandose.png)
### Para detener un contenedor

```
docker stop <nombre contenedor>
```
![ejecutandose](Seccion3/DetenerContenedor.png)

![ejecutandose](Seccion3/DetenerContenedorVisual.png)
### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

![ejecutandose](Seccion3/EjecucionComando.png)
# COMPLETAR

**¿Qué sucede luego de la ejecución del comando?**

Se ejecuta inicialmente el Docker-entrypoint.sh por defecto, para luego llamar a Docker-entrypoint.d. Se buscan las configuraciones de la imagen y luego se permite la escucha a través de ipv6, adicionalmente se preparan las variables de entorno y se modifican los procesos de trabajo.
Tras la finalización de las configuraciones, se da inicio al servidor, mostrando la versión con la que se esta trabajando, los limites de los recursos que se están utilizando y el manejo de solicitudes html. 
El terminal queda ligado a la ejecución del contenedor, por lo que es imposible realizar algún cambio a menos que antes de realizar la ejecución con el comando run, pongamos la opción -d la cual permite desligar el terminal de comandos de la ejecución del contenedor.

# COMPLETAR  

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

![ejecutandose](Seccion3/CrearYEjecutar.png)

![ejecutandose](Seccion3/CrearYEjecutar2.png)
# COMPLETAR

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

![eliminar contenedor hello](Seccion3/EliminarContenedor.png)
# COMPLETAR

Verificar que el contenedor que se eliminó

![Verificar que se elimino](Seccion3/VerificarEliminar.png)
# COMPLETAR

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```

Eliminar el contenedor **srv-web3** 

![eliminar ejecutandose](Seccion3/EliminarWeb3.png)
# COMPLETAR

Verificar que el contenedor que se eliminó

![verificar eliminar web 3](Seccion3/VerificarEliminarWeb3.png)
# COMPLETAR

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

![inspeccionar](Seccion3/InspeccionarWeb.png)
# COMPLETAR
