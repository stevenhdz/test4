# WELCOME

Inicialmente, la prueba al leerla fue muy buena, con base a CMS que había manejado, tenía una noción de como hacerlo, lo cual me llevo a usar DRAG AND DROP el cual usa canvas, sin embargo, pase a usar vue js en el frontend, ya que tenía más experiencia con el mismo y sabía que me iba a tomar menos tiempo realizar una página o landing page dinámica ademas de poder ejecutar el sass que nos cambia y aplica los estilos totales y fuentes, partiendo del lado del cliente se me presento varias dudas una de ellas era si lo hago con componentes y un for que permita duplicarlos o llenar la información estaría bien, pero si analizamos el cliente es mejor darle la comodidad como poder mover los componentes de un lado a otro, para esto use varias metodologías; sin embargo, al ir construyendo fui anexando varios componentes que nos logran permitir crear una buena interfaz, vamos al lado del servidor donde use nodejs con MVC y buenas prácticas con base a OWASP donde se usó TLS y SSL además de certificados firmados por mí para dar un mejor entendimiento a mi api, iba a iniciar la parte de roles, pero no alcance, pero la sé hacer espero le haya gustado todo lo que plante para que funcionara el mismo, tener en cuenta que la BD mongo es la CLOUD, ya que me ayuda a persistir los últimos cambios que hice para que la vieran. 

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
 
### BD se conecta a un usuario temporal, sin embargo esta con la IP 0.0.0.0 para que puedan hacer uso de la peticiones.
 

