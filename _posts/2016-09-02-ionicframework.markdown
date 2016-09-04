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
    <title>MyApp</title>
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
        <h1 class="title">MyApp</h1>
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
```
E chega um dos momentos mais importantes... Testar o aplicativo e ver o processo do seu desenvolvimento. Aqui serão apresentadas três formas diferentes para realizar testes durante o desenvolvimento. Vamos as formas de teste!

```text
O primeiro método de teste consiste no Desktop Browser test. 
Vá na pasta onde encontra o projeto criado por meio do terminal e digite: 
```
```shell
$ ionic serve
```
Ao executar o comando acima, será criado um servidor local em seu computador, permitindo que você observe o resultado pelo código desenvolvido em HTML, CSS e JavaScript.

```text
O segundo método de teste é realizando a simulação do app com base na plataforma (Ios, Android) desejada.
No terminal, execute a instrução:
```
```shell
$ ionic build "plataforma"
$ ionic emulate "plataforma"
```
Obs: no campo "plataforma" basta apenas modificar para ios ou android, de acordo com o seu objetivo.

```text
Por fim, existe a possibilidade de testar um aplicativo hibrido diretamente em um ambiente nativo, 
ou seja, diretamente em um dispositivo móvel. 
Em dispositivos Android, o procedimento é bastante simples. 
Basta conectar o dispositivo móvel no desktop/notebook e executar o comando:
```
```shell
$ ionic run android
```
<h3 section="header">Chegamos na ultima etapa de criação como um app no Ionic...</h3>
 
<img src="http://s2.quickmeme.com/img/bc/bc11fad8017bea5537859c64ec345f8e6c0503ca66051b2c470c15ec852c7775.jpg"/>

Continuando o processo de desenvolvimento com base no código utilizado neste artigo, usaremos o ng-repeat, por meio do AngularJs para adicionar algumas caracteristicas de plataformas nativas. Com isso, adicione o ng-repeat ao seu código HTML deixando-o com a seguinte estrutura:

```html
<!-- Center content -->
<ion-side-menu-content>
  <ion-header-bar class="bar-dark">
    <h1 class="title">MyApp</h1>
  </ion-header-bar>
  <ion-content>
    <!-- our list and list items -->
    <ion-list>
      <ion-item ng-repeat="task in tasks">
        {{task.title}}
      </ion-item>
    </ion-list>
  </ion-content>
</ion-side-menu-content>
```
Agora vamos adicionar um controlador AngularJs ao aplicativo. Na tag "body" do seu HTML adicione o trecho de código:
```html
<body ng-app="MyApp" ng-controller="MyAppCtrl">
```
Após realizar o passo acima, vá até o arquivo "app.js" para definir o funcionamento do controlador e insira o código:
```javascript
angular.module('MyApp', ['ionic'])

.controller('MyAppCtrl', function($scope) {
  $scope.tasks = [
    { title: 'Collect coins' },
    { title: 'Eat mushrooms' },
    { title: 'Get high enough to grab the flag' },
    { title: 'Find the Princess' }
  ];
})
```
Execute o app novamente por meio dos métodos de teste novamente e veja os resultados. 

Também podemos adicionar um Modal ao aplicativo, capaz de realizar transições para elementos diferentes do app. No nosso caso, ele permite a mudança de uma "task" para uma "task" diferente. Após o fechamento da tag ion-side-menu, basta adicionar ao código um novo script dessa forma:

```html
<script id="new-task.html" type="text/ng-template">

  <div class="modal">

    <!-- Modal header bar -->
    <ion-header-bar class="bar-secondary">
      <h1 class="title">New Task</h1>
      <button class="button button-clear button-positive" ng-click="closeNewTask()">Cancel</button>
    </ion-header-bar>

    <!-- Modal content area -->
    <ion-content>

      <form ng-submit="createTask(task)">
        <div class="list">
          <label class="item item-input">
            <input type="text" placeholder="What do you need to do?" ng-model="task.title">
          </label>
        </div>
        <div class="padding">
          <button type="submit" class="button button-block button-positive">Create Task</button>
        </div>
      </form>

    </ion-content>

  </div>

</script>
```
<blockquote> O script inserido no código acima, serve para definir o template do app como um Angular template. Nele também estão contidas as ações realizadas após o uso de buttons, com as funções manipuladoras de criação e fechamento de "tasks", juntamente com um form que recebe o nome da tarefa a ser criada, que por sua vez é disparada por meio do button de confirmação</blockquote>

Assim, faz-se necessário gerar um button dentro do ion-side-menu, certo? Certo! Então vamos adiciona-lo deixando o menu desse jeito:
```html
 <!-- Center content -->
  <ion-side-menu-content>
    <ion-header-bar class="bar-dark">
      <h1 class="title">MyApp</h1>
      <!-- New Task button-->
      <button class="button button-icon" ng-click="newTask()">
        <i class="icon ion-compose"></i>
      </button>
    </ion-header-bar>
    <ion-content>
      <!-- our list and list items -->
      <ion-list>
        <ion-item ng-repeat="task in tasks">
          {{task.title}}
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-side-menu-content>
```
Também é necessário realizar as adições ao código criado para o controlador AngularJs:
```javascript
.controller('MyAppCtrl', function($scope, $ionicModal) {
  // No need for testing data anymore
  $scope.tasks = [];

  // Create and load the Modal
  $ionicModal.fromTemplateUrl('new-task.html', function(modal) {
    $scope.taskModal = modal;
  }, {
    scope: $scope,
    animation: 'slide-in-up'
  });

  // Called when the form is submitted
  $scope.createTask = function(task) {
    $scope.tasks.push({
      title: task.title
    });
    $scope.taskModal.hide();
    task.title = "";
  };

  // Open our new task modal
  $scope.newTask = function() {
    $scope.taskModal.show();
  };

  // Close the new task modal
  $scope.closeNewTask = function() {
    $scope.taskModal.hide();
  };
})
```
Try it yourself! 

Não menos importante, a capacidade de adicionar novos projetos ao app é mencionada pelos criadores do Ionic e faz parte do processo de desenvolvimento no seu primeiro aplicativo. Para habilitar essa funcionalidade, atualize o "Center Content" e o "Left Menu" do Index.html, deixando-os dessa forma:
```html
<!-- Center content -->
<ion-side-menu-content>
  <ion-header-bar class="bar-dark">
    <button class="button button-icon" ng-click="toggleProjects()">
      <i class="icon ion-navicon"></i>
    </button>
    <h1 class="title">{{activeProject.title}}</h1>
    <!-- New Task button-->
    <button class="button button-icon" ng-click="newTask()">
      <i class="icon ion-compose"></i>
    </button>
  </ion-header-bar>
  <ion-content scroll="false">
    <ion-list>
      <ion-item ng-repeat="task in activeProject.tasks">
        {{task.title}}
      </ion-item>
    </ion-list>
  </ion-content>
</ion-side-menu-content>

<!-- Left menu -->
  <ion-side-menu side="left">
    <ion-header-bar class="bar-dark">
      <h1 class="title">Projects</h1>
      <button class="button button-icon ion-plus" ng-click="newProject()">
      </button>
    </ion-header-bar>
    <ion-content scroll="false">
      <ion-list>
        <ion-item ng-repeat="project in projects" ng-click="selectProject(project, $index)" ng-class="{active: activeProject == project}">
          {{project.title}}
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-side-menu>
```
Por fim, é necessário fazer uma ultima e considerável modificação no arquivo app.js, para habilitar as funcionalidades de criaçao, carregamento e salvamento de projetos. A versão final do app.js deverá ficar assim:

```javascript
angular.module('todo', ['ionic'])
/**
 * The Projects factory handles saving and loading projects
 * from local storage, and also lets us save and load the
 * last active project index.
 */
.factory('Projects', function() {
  return {
    all: function() {
      var projectString = window.localStorage['projects'];
      if(projectString) {
        return angular.fromJson(projectString);
      }
      return [];
    },
    save: function(projects) {
      window.localStorage['projects'] = angular.toJson(projects);
    },
    newProject: function(projectTitle) {
      // Add a new project
      return {
        title: projectTitle,
        tasks: []
      };
    },
    getLastActiveIndex: function() {
      return parseInt(window.localStorage['lastActiveProject']) || 0;
    },
    setLastActiveIndex: function(index) {
      window.localStorage['lastActiveProject'] = index;
    }
  }
})

.controller('TodoCtrl', function($scope, $timeout, $ionicModal, Projects, $ionicSideMenuDelegate) {

  // A utility function for creating a new project
  // with the given projectTitle
  var createProject = function(projectTitle) {
    var newProject = Projects.newProject(projectTitle);
    $scope.projects.push(newProject);
    Projects.save($scope.projects);
    $scope.selectProject(newProject, $scope.projects.length-1);
  }


  // Load or initialize projects
  $scope.projects = Projects.all();

  // Grab the last active, or the first project
  $scope.activeProject = $scope.projects[Projects.getLastActiveIndex()];

  // Called to create a new project
  $scope.newProject = function() {
    var projectTitle = prompt('Project name');
    if(projectTitle) {
      createProject(projectTitle);
    }
  };

  // Called to select the given project
  $scope.selectProject = function(project, index) {
    $scope.activeProject = project;
    Projects.setLastActiveIndex(index);
    $ionicSideMenuDelegate.toggleLeft(false);
  };

  // Create our modal
  $ionicModal.fromTemplateUrl('new-task.html', function(modal) {
    $scope.taskModal = modal;
  }, {
    scope: $scope
  });

  $scope.createTask = function(task) {
    if(!$scope.activeProject || !task) {
      return;
    }
    $scope.activeProject.tasks.push({
      title: task.title
    });
    $scope.taskModal.hide();

    // Inefficient, but save all the projects
    Projects.save($scope.projects);

    task.title = "";
  };

  $scope.newTask = function() {
    $scope.taskModal.show();
  };

  $scope.closeNewTask = function() {
    $scope.taskModal.hide();
  }

  $scope.toggleProjects = function() {
    $ionicSideMenuDelegate.toggleLeft();
  };


  // Try to create the first project, make sure to defer
  // this by using $timeout so everything is initialized
  // properly
  $timeout(function() {
    if($scope.projects.length == 0) {
      while(true) {
        var projectTitle = prompt('Your first project title:');
        if(projectTitle) {
          createProject(projectTitle);
          break;
        }
      }
    }
  }, 1000);

})
```
<h2 section="heading">Concluindo...</h2>
Realizando todos esses passos e por fim atualizando o seu arquivo app.js, você finalmente será capaz executar um app e compreender como funciona o Ionic, além de poder dar inicio ao processo de desenvolvimento do seu próprio aplicativo hibrido para dispositivos móveis. 
