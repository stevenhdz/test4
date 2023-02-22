# WELCOME

Estoy dispuesto a cualquier reto, me encanta aprender y demostrar mi conocimiento.

Inicialmente, la prueba al leerla fue muy buena, con base a CMS que había manejado, tenía una noción de como hacerlo, lo cual me llevo a usar DRAG AND DROP el cual usa canvas, sin embargo, pase a usar VUE JS SPA OR PWA en el frontend, ya que tenía más experiencia con el mismo y sabía que me iba a tomar menos tiempo realizar una página o landing page dinámica ademas de poder ejecutar el SCSS preprocesador que nos cambia y aplica los estilos totales y fuentes con base al observador, partiendo del lado del cliente se me presento varias dudas una de ellas era si lo hago con componentes y un for que permita duplicarlos o llenar la información estaría bien, pero si analizamos el cliente es mejor darle la comodidad como poder mover los componentes de un lado a otro, para esto use varias metodologías; sin embargo, al ir construyendo fui anexando varios componentes que nos logran permitir crear una buena interfaz, vamos al lado del servidor donde use nodejs con MVC y buenas prácticas con base a OWASP donde se usó TLS y SSL además de certificados firmados por mí para dar un mejor entendimiento a mi api, iba a iniciar la parte de roles, pero no alcance, pero la sé hacer espero le haya gustado todo lo que plante para que funcionara el mismo, tener en cuenta que la BD mongo es la CLOUD, ya que me ayuda a persistir los últimos cambios que hice para que la vieran. 

Ejemplo modelo:

![Example](https://raw.githubusercontent.com/stevenhdz/test4/master/cms/Captura%20de%20pantalla%202023-02-16%20a%20la(s)%202.39.16%20a.m..png "Example")

En este ejemplo base vamos a encontrar un boton en la parte inferior derecha donde nos va a permitir crear los componentes con una informacion
sin embargo cabe destacar que algunos de estos permiten modificarlos de una manera mas dinamica, una vez agregamos un componente a la lista de 10 posiciones el va a queda ubicado sin embargo podra ser movido arrastrandolo, al moverlo se nos desplegara dos botones mas uno de edicion otro de eliminacion, con la finalidad de poder dar ese CRUD de forma sencilla, cada vez que guardarmos o editamos tomaria cambios al refrezcar se notaran los cambios.

Componentes actuales:

```html
Text -> titulos
Button -> podras color un enlace ademas del nombre
Slider -> imagenes separadas por el simbolo , 
Html -> podras embeber html enriquecido
image -> podras color una imagen o varias, tener en cuenta que si pone varias se podra dar clic y abrir un visualizador, cuando usar una ejemplo un logo.
```

Como se inicio la aplicacion:

  FRONTEND: como lo dice la documentacion oficial

```sh
npm install -g @vue/cli
vue create cms
```

  sass: con base a assets base2.scss y la carpeta scss donde tengo todo desglozado para que se apliquen los estilos.
  
  ```sh
sass --watch sass:css

```

  pwa: convertirla a aplicacion
  
    
  ```sh
vue add pwa
npm run build && npx http-server dist
```
  
    
  BACKEND: como lo dice la documentacion oficial
  
  **Install**

```sh
  npm init -y
  npm i express mongoose bcrypt dotenv @hapi/joi nodemon cors fs https method-override morgan axios colors
  npm run dev
```

  **Importante generar los certificados ssl/tls**

    *  openssl genrsa -out key.pem

    *  openssl req -new -key key.pem -out csr.pem

    *  openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out cert.pem
  


Como usar la aplicacion:

  FRONTEND: debemos bajar el repo e hacer los sgtes pasos

```sh
cd cms
  npm install
  npm run lint
  npm run dev
```
    
  BACKEND: debemos bajar el repo e hacer los sgtes pasos
  
```sh
  cd services
    npm install
    npm run dev ó node app.js
    npm run start
  ```
  
  Documentacion de las apis:
  

### nos permite poder traer toda la informacion

```http
GET https://localhost:3001/api/commit/ HTTP/2.0
Content-type: application/json
  ```


### nos permite poder consultar de a uno

```http
GET https://localhost:3001/api/commit/1 HTTP/2.0
Content-type: application/json
 ```

### nos permite poder actualizar de a uno

```http
PUT https://localhost:3001/api/commit/63ee5cc7a22b045e6c1ba4a0 HTTP/2.0
Content-type: application/json

{
    "id": "1",
    "cms":[example]
}
 ```


### nos permite poder eliminar de a uno

```http
DELETE https://localhost:3001/api/commit/1 HTTP/2.0
Content-type: application/json
 ```
 
 
### nos permite crear

```http
POST https://localhost:3001/api/commit/ HTTP/2.0
Content-type: application/json

{
    "id": "1",
    "cms":[]
}
 ```

### En caso de no consumir las apis bien: si ya tiene el servidor backend arriba seria consumirla desde la URI y autorizar https://localhost:3001/api/commit/
 
### BD se conecta a un usuario temporal, sin embargo esta con la IP 0.0.0.0 para que puedan hacer uso de la peticiones.

# ARQUITECTURA

![Example2](https://raw.githubusercontent.com/stevenhdz/test4/master/cms/Captura%20de%20pantalla%202023-02-16%20a%20la(s)%203.30.49%20p.m..png "Example2")

