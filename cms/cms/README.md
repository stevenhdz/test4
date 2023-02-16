
## PRIMERO QUE TODO LO REALICE EN VUEJS YA QUE MI CONOCIMIENTO ES AVANZADO EN EL MISMO Y CON REACT ME HUBIERA TOMADO MAS TIEMPO SIN EMBARGO ESTO NO QUIERE DECIR QUE NO LO SEPA, ESPERO NO HAYA PROBLEMA CON ELLO.


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

