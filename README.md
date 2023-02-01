# Reporting

* [Primeros pasos](#primeros-pasos)
* [Modo CLI](#modo-cli)
* [Modo Aplicación Web](#modo-aplicación-web-frontend--backend)
* [Despliegue en Docker](#despliegue-en-docker)

*Para detalles más específicos de cada uno de los servicios mirar su repositorio correspondiente*

## Primeros pasos
El primer paso para poder poner en marcha el proyecto es, clonar el repositorio e instalar las dependencias necesarias mediante npm.
```
git clone --recurse-submodule -j8 git@github.com:SalvaChiLlo/Reporting.git

cd Reporting

npm install
```
## Modo CLI
Para ejecutar la solución como una herramienta de terminal podemos ejecutar el siguiente comando.
En la carpeta sample se encuentran los diferentes archivos de entrada de ejemplo.

La herramienta require que se le pasen las opciones *customers*, *products* y *orders* junto con la ruta que indica la posición del archivo. 
No se requiere ningún orden específico de las órdenes.
```
./reporting --customers ./sample/customers.csv --products ./sample/products.csv --orders ./sample/orders.csv
```

## Modo Aplicación Web (Frontend + Backend)
La solución también se encuentra como una aplicación web con una página web realizada con Angular, la cual, realiza peticiones al backend que expone una API que permite recibir 3 archivos y con estos se llama a la funcionalidad deseada.
Para lanzar a ejecución tanto el servidor del frontend como el del backend, ejecuta cada comando en una ventana de terminal.
```
npm run serveBack
npm run serveFront
```
* Se debería de abrir una pestaña en el navegador con la aplicación en funcionamiento.
* Por defecto, el backend se ejecutará en el puerto `8080`. Si se desea cambiar, simplemente hay que cambiar la variable de entorno del archivo `.env` en el directorio ReportingBackend.

## Despliegue en Docker
Si quieres probar la herramienta pero no quieres instalar ninguna dependencia, puedes utilizar Docker.
En este [docker-compose.yml](https://github.com/SalvaChiLlo/Reporting/blob/main/docker-compose.yml) encontrarás la definción de los servicios, la cual, podrás lanzar a ejecución con el comando `docker-compose up -d`.

Una vez lanzado, con la configuración por defecto, podrás acceder a la aplicación web a través de [http://localhost](http://localhost)