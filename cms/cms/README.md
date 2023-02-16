
Inicialmente, la prueba al leerla fue muy buena, con base a CMS que había manejado, tenía una noción de como hacerlo, lo cual me llevo a usar drag and drop el cual usa canvas, sin embargo, pase a usar vue js en el frontend, ya que tenía más experiencia con el mismo y sabía que me iba a tomar menos tiempo realizar una página o landing page dinámica, partiendo del lado del cliente se me presento varias dudas una de ellas era si lo hago con componentes y un for que permita duplicarlos o llenar la información estaría bien, pero si analizamos el cliente es mejor darle la comodidad como poder mover los componentes de un lado a otro, para esto use varias metodologías; sin embargo, al ir construyendo fui anexando varios componentes que nos logran permitir crear una buena interfaz, vamos al lado del servidor donde use nodejs con MVC y buenas prácticas con base a OWASP donde se usó TLS y SSL además de certificados firmados por mí para dar un mejor entendimiento a mi api, iba a iniciar la parte de roles, pero no alcance, pero la sé hacer espero le haya gustado todo lo que plante para que funcionara el mismo, tener en cuenta que la BD mongo es la CLOUD, ya que me ayuda a persistir los últimos cambios que hice para que la vieran. 


# cms

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```



cd cms
  npm install
  npm run lint
  npm run dev
  
  
  
para las apis la documentacion es :

En la carpeta cliente encontrar los endpoint con sus respectivas URIS 

### all

GET https://localhost:3001/api/commit/ HTTP/2.0
Content-type: application/json


### one

GET https://localhost:3001/api/commit/1 HTTP/2.0
Content-type: application/json

### update one

PUT https://localhost:3001/api/commit/63ee5cc7a22b045e6c1ba4a0 HTTP/2.0
Content-type: application/json

{
    "id": "1",
    "cms":[]
}

### delete one

DELETE https://localhost:3001/api/commit/1 HTTP/2.0
Content-type: application/json

### create

POST https://localhost:3001/api/commit/ HTTP/2.0
Content-type: application/json

{
    "id": "1",
    "cms":[]
}

