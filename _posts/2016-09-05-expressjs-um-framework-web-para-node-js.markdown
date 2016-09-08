---
layout:     post
title:      "Express.js um framework web para Node.js"
subtitle:   "Entendo e criando uma aplicação em Express.js"
date:       2016-09-5 00:00:00
author:     "Adjamilton Junior"
header-img: "img/2016-09-05-expressjs-um-framework-web-para-node-js/express_bg.jpg"
---

O mercado de desenvolvimento de software exige, cada dia mais, praticidade e velocidade, sem abandonar a segurança e robustez que as aplicações exigem. Pensando nisso e com o Javascript em foco, foi criado o ExpressJS.

## O que é ExpressJS?

Um framework web para [Node.js](https://nodejs.org/) com foco em simplicidade e velocidade. O ExpressJS é livre e de código aberto, desenvolvido sob a [licença do MIT](https://en.wikipedia.org/wiki/MIT_License). O principal objetivo desse framework é o desenvolvimento de aplicações web e APIs. Segundo seu autor original, o ExpressJS foi inspirado no servidor [Sinatra](http://www.sinatrarb.com/). Hoje, ele é o framework mais utilizado pra Node. Na pilha MEAN, o ExpressJS representa a parte de backend.

A versão atual do Express é a 4.14.0, lançada em 16 de junho de 2016. 

Site oficial do projeto: [https://expressjs.com](https://expressjs.com)

## Instalando o Express.js

Primeiro, você deve assegurar-se que tem o Node instalado. Você pode verificar digitando na linha de comando ```node -v```. 

Crie a psta da sua aplicação.

```shell
# mkdir myapp
# cd myapp
```

Inicialize sua aplicação.
```shell
# npm init
```

Esse comando irá gerar uma série de perguntas sobre sua aplicação, como versão e nome, para gerar o arquivo ```package.json```que conterá essas informações. Você pode pressionar ```Enter``` para todas.

Agora o  Express pode ser instalado:

```shel
# npm install express --save
```
A opção ```--save``` faz com que as dependências sejam salvas no arquivo ```package.json```.

## Hello World

Agora que temos o framework instalado, vamos criar nossa primeira aplicação.

Acesse o diretório da sua aplicação, liste os arquivos e veja que há um arquivo chamado ```app.js```. Inicialmente, esse arquivo vem com algumas informações que não usaremos, portanto você pode editá-lo e substituir todo seu conteúdo pelo seguite código:

```javascript
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
```

## Inicializando o Express

Agora que já instalamos, e editamos no arquivo aap.js, vamos inicializar o framework para "subir" nossa aplicação.

```shell
# node app.js
```

## Visualizando nossa aplicação

A aplicação deve ser acessada via browser, pelo endereço ```http://127.0.0.1:3000```.

## Conclusão

Express, como já falei, é um framework simples que permite que uma aplicação esteja no ar em poucos minutos, com pouquíssimo esforço.
Contudo, é um framework muito poderoso. Vale a pena investir tempo em seu aprendizado.