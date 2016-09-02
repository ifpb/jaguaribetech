---
layout:     post
title:      "p5 Processamento em JS"
subtitle:   "Aprenda a usar a biblioteca p5 e progamar com artes visuais"
date:       2016-08-31 00:00:00
author:     "Lucas Dantas"
header-img: "/img/2016-08-31-e-agora-jose/p5.jpg"
---


 <h2 class="section-heading">p5 JS Library</h2>
 
 <h4 class="section-heading">O que é p5.js? Para que serve?</h4>
 p5 js é uma biblioteca de JavaScript usada para Processamento. Mas como assim?
 Processamento é um software flexivel para se aprender a progamar dentro do contexto de artes visuais.
 Des de 2001, Processing tem promivido software on ambito de artes visuais na tecnologia. Existem milhares de estudantes, artistas, designers e pesquisadores que usam Processing para apredizagem e prototipar.
 
 <h4 class="section-heading">Como comecar a usar?</h4>
 
 Primeiramente, voce deve adicionar este CDN ao seu HTML:
 ```javascript
    <script src="//cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.3/p5.js"></script>
 ```
 
 <h5 class="section-heading">Criando seu primeiro rascunho:</h5>
 
 ```javascript
 function setup() {

}

function draw() {
  ellipse(50, 50, 80, 80);
}
 ```
 Esta linha de codigo significa "desenhe um circulo, com 50 pixels no centro da esquerda, 50 pixels de cima, com uma largura e altura de 80 pixels.
 
 Salve seu rascunho e recarregue a pagina. Se voce digitou tudo corretamente, voce vera isso:
 
 <img src="http://p5js.org/img/get-started/first-sketch.png" alt="" style="margin: 0 auto;"/>
 
 Se voce nao digitou corretamente, talvez voce nao veja nada. Se isso acontecer, verifique se voce copiou o codigo exatamente igual: os numeros devem estar em parenteses e com virgulas entre eles, e a linha deve terminar com um ponto e virgula.
 
 Agora, vamos fazer um rascunho um pouco mais bacana. Teste o seguinte codigo:
 ```javascript
 function setup() {
  createCanvas(640, 480);
}

function draw() {
  if (mouseIsPressed) {
    fill(0);
  } else {
    fill(255);
  }
  ellipse(mouseX, mouseY, 80, 80);
}
 ```
 Como voce pode ver esse codigo gera uma janela com 640 de largura por 480 pixels de altura, e em seguida comeca a desenhar circulos brancos na posicao do mouse. Quando o mouse é clicado, a cor do circulo muda para preto. 
 
 <img src="http://p5js.org/img/get-started/first-sketch2.png" alt="" style="margin: 0 auto;"/>
 
 Existem duas funcoes principais que voce ira usar. O bloco setup() é executado apenas uma vez, e é tipicamente usado para inicializacao, ou para criar um progama que nao precisa de um codigo rodando repetidamente. O bloco draw() é executado repetidamente, ele é usado para animacao.
 
 ```javascript
 var x = 0;

function setup() {
  background(100);  
}

function draw() {
  ellipse(x, height/2, 20, 20);
  x = x + 1;
}
 ```
 
  <h5 class="section-heading">Create canvas</h5>
  Por default, o drawing canvas tem tamanho 100x100. Se voce quiser colocar um tamanho customizado, use a funcao
  ```javascript
  createCanvas()
  ```
  Uma boa é sempre fazer isso na primeira linha do setup(). O codigo abaixo seta o canvas para tamanho 600x400:
  ```javascript
  function setup() {
  createCanvas(600, 400);
  line(15, 25, 70, 90);
}
  ```
  createCanvas() vai gerar um novo canvas para desenho no tamanh especificado e concatenado a sua pagina html.
  Se existir outros conteudos na body da sua pagina, ele ira ser adicionado no conteudo seguinte.
 
 O canvas pode ser afetado por algum css existente na pagina, incluindo o default. Por exemplo, muitos browsers tem padding default perto do fim da pagina. Se voce ta percebendo que o canvas nao esta no lugar apropiado, deve ser por isso. Para corrigir isso, voce deve colocar uma tag no seu <head> assim:
 
 ```javascript
 <style> body{padding:0; margin:0;} </style>
 ```
 <blockquote>Pronto!</blockquote>
 
 Agora é so ir brincando com o p5.js e testando as diversas possibilidades de facanhas que podem ser feitas com ele.
 <img src="http://i.giphy.com/xT0Gql3DlyJ0EeRAA0.gif" alt="" style="margin: 0 auto;"/>
 
 <iframe src="//giphy.com/embed/3XRVcFDw7O1AA" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/thisisfusion-congratulations-congrats-you-did-it-3XRVcFDw7O1AA">via GIPHY</a></p>
 

 
 
 
 


 
 

