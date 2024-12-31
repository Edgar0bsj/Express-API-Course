## Menu

- [Menu](#menu)
- [💻 Pré-requisitos](#-pré-requisitos)
- [📚 Criando a estrutura do projeto](#-criando-a-estrutura-do-projeto)
  - [1](#1)
  - [2](#2)
  - [3](#3)
  - [4](#4)
  - [5](#5)
  - [6](#6)
  - [7](#7)
- [📚 Configurando nodemon e sucrase](#-configurando-nodemon-e-sucrase)

## 💻 Pré-requisitos
- [x] Node.js

## 📚 Criando a estrutura do projeto
### 1
```bash
npm init -y
```

### 2
```bash
code .
```

### 3
```bash
npm install express
```

### 4
Estrutura de pasta

DEVHOUSE/
├── node_modules/       
├── package-lock.json       
├── package.json      
├── src/
│   ├── app.js      
│   ├── server.js      
│   └── routes.js      

### 5
- `DEVHOUSE/src/app.js`
```javascript
const express = require('express')
const routes = require('./routes')

class App{

    constructor(){
        this.server = express()

        this.middlewares()
        this.routes()
    }

    middlewares(){
        this.server.use(express.json())
    }

    routes(){
        this.server.user(routes)
    }
}

module.exports = new App().server
```

### 6
- `DEVHOUSE/src/server.js`
```javascript
const app = require('./app')

app.listen(3333)
```

### 7
- `DEVHOUSE/src/routes.js`
```javascript
const { Router } = require('express')

const routers = new Router()

routes.get('/', (req, res)=> {
    return res.json({ ok: true })
})

module.exports = routes
```

## 📚 Configurando nodemon e sucrase