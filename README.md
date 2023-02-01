# Reporting

- [Primeros pasos](#primeros-pasos)
- [Modo CLI](#modo-cli)
- [Modo Aplicación Web](#modo-aplicación-web-frontend--backend)
- [Despliegue en Docker](#despliegue-en-docker)
- [Enlaces de Interés/Bibliografía](#enlaces-de-interés--bibliografía)

_Para detalles más específicos de cada uno de los servicios mirar su repositorio correspondiente._

## Primeros pasos

El primer paso para poder poner en marcha el proyecto es, clonar el repositorio e instalar las dependencias necesarias mediante npm.

```
git clone --recurse-submodule -j8 git@github.com:SalvaChiLlo/Reporting.git

cd Reporting

npm install
```

## Modo CLI

Para ejecutar la solución como una **herramienta de terminal** podemos ejecutar el siguiente comando.

```
./reporting --customers ./sample/customers.csv --products ./sample/products.csv --orders ./sample/orders.csv
```

En la carpeta _sample_ se encuentran los diferentes **_archivos de entrada de ejemplo_**.

La herramienta requiere que se le pasen las opciones _customers_, _products_ y _orders_ junto con la ruta que indica la posición del archivo.

**_No se requiere ningún orden específico de los argumentos._**

## Modo Aplicación Web (Frontend + Backend)

La solución también se encuentra como una **aplicación web** con una página web realizada con **Angular**, la cual, realiza peticiones al backend que expone una **API que permite subir 3 archivos CSV** y con estos se llama a la funcionalidad deseada.
Para lanzar a ejecución tanto el servidor del frontend como el del backend, **ejecuta cada comando en una ventana de terminal**.

```
npm run serveBack
npm run serveFront
```

- Se debería de abrir una pestaña en el navegador con la aplicación en funcionamiento, sino, [http://localhost:4200](http://localhost:4200).
- Por defecto, el backend se ejecutará en el puerto `8080`. Si se desea cambiar, simplemente hay que cambiar la variable de entorno del archivo `.env` en el directorio ReportingBackend.

## **Despliegue en Docker**

Si quieres probar la herramienta pero **no quieres instalar ninguna dependencia**, puedes **utilizar Docker**.

En este __[docker-compose.yml](https://github.com/SalvaChiLlo/Reporting/blob/main/docker-compose.yml)__ encontrarás la definción de los servicios, la cual, podrás lanzar a ejecución con el comando 
```
docker-compose up -d
```

Una vez lanzado, con la configuración por defecto, podrás __acceder a la aplicación web a través de [http://localhost](http://localhost)__.

## Enlaces de interés / Bibliografía

- [Multer](http://expressjs.com/en/resources/middleware/multer.html)
- [Csvtojson](https://www.npmjs.com/package/csvtojson)
- [Ansi-colors](https://www.npmjs.com/package/ansi-colors)
- [Eslint](https://www.npmjs.com/package/eslint)
- [Dynamically set angular env variables in docker](https://nkpremices.com/dynamically-set-angular-env-variables-in-docker/)
- [Configure NGINX for Angular - Docker](https://dev.to/oneofthedevs/docker-angular-nginx-37e4)
