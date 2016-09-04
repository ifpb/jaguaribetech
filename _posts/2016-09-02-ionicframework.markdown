---
layout:     post
title:      "O Ionic framework e o desenvolvimento de apps em HTML5"
subtitle:   "May the Ionic be with you!"
date:       2016-09-02 00:00:00
author:     "Gilberto Firmino de Souza Neto"
header-img: "img/2016-09-02-ionicframework/ionic_icon.png"
---

<h2 class="section-heading"> O desenvolvimento de mobile apps em HTML5 </h2>

Quando falamos de desenvolvimento, a cada dia que passa é possível notar a existência de um movimento migratório
partindo dos desenvolvedores _web_ rumo ao campo do desenvolvimento _mobile_. E isso ocorre devido a progressão
do desenvolvimento hibrido de aplicações, facilitando o trabalho dos desenvolvedores por meio de frameworks. Desenvover aplicativos hibridos consiste na utilização de linguagens front-end como JavaScript, HTML e CSS, diferente do desenvolvimento nativo, que obrigatoriamente deve ser desenvolvido utilizando os recursos da plataforma para o qual o app está sendo desenvolvido.
  
Tudo bem, criar apps hibridos é definitivamente um ponto positivo para nós desenvolvedores, certo? Sim! Mas e quanto a interface desse aplicativo? Será que podemos criar uma mesma aplicação hibrida, que possua interfaces semelhantes com aquelas desenvolvidas nativamente?? 
  
<img src="https://cdn.meme.am/instances/400x/66555912.jpg" alt="" style="margin: 0 auto;"/>
  
Para isso foi criado o Ionic, um framework front-end criado pela Drifty, voltado para o desenvolvimento de aplicativos hibridos e que faz uso do HTML em parceria com o <a href="https://angularjs.org/">AngularJs</a> (já incluindo o JavaScript) e CSS, capaz de criar apps com UI's 
com um bom desempenho e fluidez.

<h2 class="section-heading"> O Ionic Framework </h2>

O Ionic já mencionado anteriormente é um framework que tem como objetivo, permitir que as aplicações hibridas desenvolvidas para dispositvos móveis, possam utilizar por meio de outros frameworks como o <a href="https://cordova.apache.org/">Cordova</a> (recomendado) ou <a href="http://phonegap.com/"> PhoneGap</a>, recursos de SDK's nativas. Isso permite que os aplicativos criados em HTML5, CSS e JavaScript tenham seus de custos de desenvolvimento reduzidos - pois é necessário desenvolver o app uma única vez - e sejam compativéis com diversas plataformas ao mesmo tempo, ou seja, aquele mesmo app criado por você, pode ser usado em dispositivos Android, IoS e Windows Phone (É isso mesmo, Windows Phone!), minimizando os problemas de funcionalidade.

<img src="http://www.reactiongifs.com/wp-content/uploads/2011/09/mind_blown.gif" alt="" style="margin: 0 auto;"/>

<h3> Componentes do Ionic </h3>

<img src="https://http2.mlstatic.com/curso-html5-em-video-bnus-css3-e-javascript-D_NQ_NP_882011-MLB20456508120_102015-O.jpg"/>
<img src="http://www.w3schools.com/angular/pic_angular.jpg"/>
<img src="http://devgirl.org/wp-content/uploads/2014/02/cordova_bot.png"/>

<h2 class="section heading"> Como instalar o Ionic </h2>

Agora que conhecemos o poder do Ionic, vamos aprender a fazer deste framework incrível! 

Em primeiro lugar, você deve ter o <a href="https://nodejs.org/en/">NodeJs</a> instalado em seu computador.

<blockquote>Verifique se o node esta instalado em seu computador rapidamente no terminal digitando o seguinte comando: `node -v`.</blockquote>

Após a verificação e instalação do NodeJs (caso não o possua), vamos a instalação do Cordova. Abra o terminal e digite o seguinte comando:

```shell
$ sudo npm install -g cordova
```

Após a instalação do Cordova com êxito, em seguida iremos instalar o Ionic por meio do seguinte comando, também executado via terminal:

```shell
$ sudo npm install -g ionic
```

Simples, não é? Agora já podemos dar inicio a um projeto para a criação de um app. Ainda no terminal, digite:

```shell
$ ionic start myApp blank
```

<blockquote>O nome "MyApp" pode ser substituido pelo nome que você deseja dar ao projeto criado.</blockquote>

Apos a execução do comando acima, o Ionic apresenta um help menu com o seguinte layout:


<img src="http://tutsmais.com.br/blog/wp-content/uploads/2015/04/Screen-Shot-2015-04-30-at-00.20.05.png"/>

```text
Em seguida será criado um diretório com o nome dado ao projeto, que pode ser acessado pelos comandos $ cd "MyApp" && ls, gerando a listagem de arquivos existentes na pasta criada.
```
Agora é necessário informar ao Ionic quais plataformas serão usadas e consequentemente configuradas.

<blockquote> Para plataforma Android execute o seguinte comando: </blockquote>
```shell
$ ionic platform add android
```
<blockquote> Para plataforma IoS execute o seguinte comando: </blockquote>
```shell
$ ionic platform add ios
```

Agora vamos testar se o projeto criado esta funcionando corretamente.

<blockquote> Para projetos voltados p/ Android execute o seguinte comando: </blockquote>
```shell
$ ionic build android
$ ionic emulate android
```
<blockquote> Para projetos voltados p/ IoS execute o seguinte comando: </blockquote>
```shell
$ ionic build ios
$ ionic emulate ios
```

<h3 section="header"> Criando um app no Ionic </h3> 

Finalmente, vamos aprender a criar um mobile app no Ionic, utilizando suas ferramentas.

Primeiramente é preciso criar um documento index.html que será a main page do aplicativo desenvolvido. Criaremos esse documento com a seguinte estrutura:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Todo</title>
    <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no, width=device-width">

    <link href="lib/ionic/css/ionic.css" rel="stylesheet"> <!-- Referência para utilização dos recursos CSS do IONIC -->

    <script src="lib/ionic/js/ionic.bundle.js"></script> <!-- Referência para utilização dos recursos JS e Angular do IONIC -->

    <!-- Needed for Cordova/PhoneGap (will be a 404 during development) -->
    <script src="cordova.js"></script> <!-- Referência para utilização dos recursos do Cordova -->
  </head>
  <body>
  </body>
</html>
```

Hora de utilizar as funcionalidades CSS, JavaScript e Angular no nosso projeto! 

Uma das várias funcionalidades do Ionic, é a criação de menus laterais, ou Ion-side-menu, oferencendo uma experiência bastante interssante ao usuário no que diz respeito a navegação por menus dentro do app criado. 

Para incluir o ion-side menu basta adicionar ao Index.html, dentro da tag o seguinte trecho de código:

```html
<body>
  <ion-side-menus>
    <ion-side-menu-content>
    </ion-side-menu-content>
    <ion-side-menu side="left">
    </ion-side-menu>
  </ion-side-menus>
</body>
```
<blockquote> A estrutura de menus do seu app ficará mais ou menos assim: </blockquote>

<img src="http://ionicframework.com.s3.amazonaws.com/guide/0.1.0/3-mockup.png"/>

Ei! Mas não é só isso ok? O Ionic tem diversas funcionalidades desenvolvidas com o AngularJs, junto com a estilização por meio do CSS, que permitem a criação de um mobile app "de respeito". Então seguem os links para você "curtir" e também "compartilhar", é claro!

<blockquote><a href="http://ionicframework.com/docs/api/">JavaScript Components</a></blockquote>
<blockquote><a href="http://ionicframework.com/docs/components/">CSS Componentes</a></blockquote>

<img src="http://i2.kym-cdn.com/photos/images/original/000/538/716/7f5.gif"/>

Agora que você já descobriu a amplitude do Ionic, é hora de dar vida ao seu app, ou seja, transformar o código desenvolvido em algo funcional. Para isso, é necessário criar um arquivo no diretório "MyApp/js" com o nome app.js . Em seguida, insira o seguinte código no arquivo:

```javascript
angular.module('MyApp', ['ionic'])
```
Feito isso, volte ao seu arquivo Index.html e antes da tag que referência o Cordova insira o script:
```html
<script src="js/app.js"></script>
```
Por fim, modifique o <body> do seu Index.html deixando-o com essa estrutura:

```html
<body ng-app="MyApp">
  <ion-side-menus>

    <!-- Center content -->
    <ion-side-menu-content>
      <ion-header-bar class="bar-dark">
        <h1 class="title">Todo</h1>
      </ion-header-bar>
      <ion-content>
      </ion-content>
    </ion-side-menu-content>

    <!-- Left menu -->
    <ion-side-menu side="left">
      <ion-header-bar class="bar-dark">
        <h1 class="title">Projects</h1>
      </ion-header-bar>
    </ion-side-menu>

  </ion-side-menus>
</body>
