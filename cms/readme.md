# WELCOME

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
 
### BD se conecta a un usuario temporal, sin embargo esta con la IP 0.0.0.0 para que puedan hacer uso de la peticiones.

# ARQUITECTURA

![Example](https://viewer.diagrams.net/index.html?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1#R7Vxbk6I4FP41PmoB4fo4arszVdO7UztbtbNPVoSImQZiQWjt%2BfWbQFAgKIw2jX3pF8lJSCDfd04OJyc9ArNw%2F0cMt5t74qFgpCnefgTmI01TdaCzHy55yiWWJQR%2BjD3R6Cj4jn8hIVSENMUeSioNKSEBxduq0CVRhFxakcE4JrtqszUJqqNuoY8kwXcXBrL0X%2BzRTS61Neso%2F4ywvylGVk0nrwlh0Vi8SbKBHtmVROBuBGYxITS%2FCvczFPDJK%2BYlv29xovbwYDGKaJcbVl%2BU%2Fedo%2B%2BPPz75CZsRy0O7fsZb38giDVLzwFLoPKPLEM9OnYiKSHQ4DGLHSNKEwpgIqhZXXOAhmJCBx1hJ4ENlrN2sXkwdUqjFdG63WrEaMimKK9idfRz1MEmMXIiGi8RNrIm4wxbQKXqlAlHdHlIAjZJsSQrouhFAwwz90fRjtb8YkGPns1Q%2FDWbXhdHk4o2m02mAwoCiOIEVTkkZeUgaMXZTe8yjKYPwNSHUJUglLDyYb5An0SEoDHDGYCgXiwg0N2aBzlV3CAPsRu3YZMIgBOQ3gCgXfSIIpJpUKjidmqvO11mBFKCVhqcEn0SUlW06TDdzyBwv3Prchkx1aBcQnySQkkU%2B8VSeynGb3SQZpVUg1MLElTHV1ojWgahbSJhJVAP1d9Ix29GCyzYFa4z1HcbpFMWajcwzmbAhmGtG3o%2BgslgejxEGv0CLZQhdH%2Fj8cojlgAhxmprL4nePQZ28YYIbPAroUP6Klh2P2ZIRPwwLzESJEl25AUm%2BSPPpd9f4CKI0qlMCeGJ3UE6hFw2cH8mD2j8Ahjy0tokhiumEkj2Bwd5ROY24Vjpp5aPOVZDBwCH8iSp%2BE8YUpJVWA2STGTz%2F4%2FRNFMQrBf5nABEV5vhcj5KWncqnEnFy4x%2FRH0Tu7zvsyROnYEy88lQr1fvLZ4FNwAfBsGkkau%2BhMO1M4BzD20bn%2B1BNMilEAOYmrHsSzs0LWbzdGbD1oJEtmSFs0uG5TQ%2Bx5OZdQgn%2FBVVCs0lvCVDJ7H2M6MubntFE4U%2BLmowvTDpbSPLmie8ZBU69o6hjkxc6zL%2Fr%2Bxl%2Bm1ISs1wmDvYfltHiY167HN6N%2FYFD9MyX9S7fe29G%2F8z4zs9u2qt28xskuz4fGXaNx%2BqAaZ0kaF%2BCEvhF9O%2B%2BWMn1jf5UFz7h57QNDaN%2FN6IoxqK7YjbryV%2FRWlqcTa%2F9BXXRNVSvqot%2B8uugfi9WzKqA5qAI6kgJ6KEBvxj084Qkc9c%2B0nYr%2BjW9eAWWHXsKqMcJZCXZdGLmU0C4xoR7VhLsETGDkxYS%2FTj1mbs9mps5mZsoae5h1V9RFJAu5n%2BTC8wbONAM0RM50dWIJaTl4Zpi9Bc%2BKj5RzqCYPiLqbkRSvrgC722CKeCiT37RjQMhTr9mWcac1bVessz9JN6e50dVmma1lP1xdtVlWoWZirSZ1GqVZF%2FWWzomOrexuVt%2FQiVqTcTei0jYzJ60cb7VdzeH6h3SVBXpRMsEu73G6jb9kF3O4xX0RF6jVQJLRcT%2FG7oux4IOxH4z9Hcaq6tCU7bBT%2BEHZD8qWKGupHTfW%2BiNthw3SD9K%2Bb9Jak2rMTeuarNEbaTt8pHyQ9l2TVqtaWjC0cyC7s4uYsIm8LjPMQLanN3HT1lbANLt%2B6J7f5dJ7SQ27bjYHiRKOLozpFTsAbTE9sbPTHtM7gdfLxPTk%2FSeZwcIGFClOpTlsNhqtxifLkeOplH6GYpMVzgb7VORycYilxK4i1WpDKU93%2FcQnQlu4XqRmtmmNGT%2FiictG1BYepJCnXTF5wn7TKLsa88DX%2BJEEPE624EZm8Ziin8lY1ezJNvIvt2fnQ%2FmaU40jag3mzJY10OjLnMkbK6%2BfBKCVBDu0GnvoEQVkGzI0xzDyxglNPUxYpcGDbAvTdJZeDP1lSFY4QEsPJewdlylepvveSWI5NU8NNJhqx5J5UsienSdy%2FF%2FiiQRQiShyEF%2FyQgp6rdlqKiy3qo1OpFX%2BSmPE3yiEEavlGC598sgziCNmmbXFfSb3lnOUPDBSXp1l2YJXLcvSlMEyG5TaBL1lywJriHW1tPvG%2FbbS7tuY%2BdK6dcn%2B26U59P2t7sVObOvy7gy5uhdP%2BaYse%2FvyTtZr7KJxvsar1sGc4yBljIEuQclS0ceK1bcNV4FddbYbVnpVa7AKB%2BHzGwWZAS9rFCxg9GIU1mtkuo1GwbOclXLNNn5XowBeyihkt36KY%2FhUaiCW12PPxTbz%2BUM6i4uas4t8%2FGfdrgaDpFcdyTmq5IoYLax8xQS0b4CAmn2egJpyXXtgOS%2FAWHmFnQU8RUFOimldN08fNzqXSnEicJdxsDiU2ZRyERL3Id2yBTSikH0Gx8kkTVB8n53tbHCssr9qjZZXKYrtrjufW7zEs67tszQ41g3xKrO3cJU5hJG6PRcYGC9kbK5DS94Sm7Mvej4Uj9YqXswAqOPJCExHvaWucXAT8XErIShSmspwX53l1OKk6lbVzjaEGQ7b8ZXzgX1pmCpHJSPioZ9sbVGyzwAlfHTfEGjnI%2FZ2bVkz5E1mVXlReJwhDGAHc1YcRmv9eLc7Wq6ciIN9vctx2fvi0LeSHRx%2BNzpQOyeiOg068KImqui4hE22dfBuELHMWhqB0vFQeW%2BI2K%2FdKmkdrdKgRgkMYvwv%2FUR%2FTnjAa4Cn2KR%2Ff%2FDorwKegc%2FLDwdP14%2FFa%2BG5KDJlODUf29HLULe2V18i1KQPHLkfjjtdj8fdBHd08xa5I2esze6%2FS3wqJatlyZTfq8mUkt9znU9fmwdFDjvYTT69bv%2B%2BCzniCXrF%2F5LLJ%2FX4H%2FnA3f8%3D "Example")
 

