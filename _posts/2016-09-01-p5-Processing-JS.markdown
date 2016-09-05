---
layout:     post
title:      "p5.js - Processing em JS"
subtitle:   "Aprenda a usar a biblioteca p5 e progamar com artes visuais. O que é p5.js? Para que serve?"
date:       2016-09-01 01:00:00
author:     "Lucas Dantas"
header-img: "img/2016-09-01-p5-Processing-JS/p5.png"
---

p5 js é uma biblioteca de JavaScript usada para Processing. Mas como assim?

Processing é um software flexível para se aprender a progamar dentro do contexto de artes visuais.

Desde 2001, Processing tem promivido software no âmbito de artes visuais na tecnologia. Existem milhares de estudantes, artistas, designers e pesquisadores que usam Processing para apredizagem e prototipar.

<h4 class="section-heading">Como comecar a usar?</h4>

Primeiramente, você deve adicionar este CDN ao seu HTML:

```javascript
    <script src="//cdnjs.cloudflare.com/ajax/libs/p5.js/0.5.3/p5.js"></script>
```

<h5 class="section-heading">Criando seu primeiro rascunho:</h5>

Para criar o primeiro rascunho você irá colocar o seguinte código no seu editor de texto:

```javascript
 function setup() {
 }

 function draw() {
   ellipse(50, 50, 80, 80);
 }
```

Esta linha de código significa "desenhe um circulo, com 50 pixels no centro da esquerda, 50 pixels de cima, com uma largura e altura de 80 pixels.

Salve seu rascunho e recarregue a página. Se você digitou tudo corretamente, vera isso:

<img src="http://p5js.org/img/get-started/first-sketch.png" alt="" style="margin: 0 auto;"/>

Se você não digitou corretamente, talvez você não veja nada. Se isso acontecer, verifique se você copiou o código exatamente igual: os numeros devem estar em parenteses e com vírgulas entre eles, e a linha deve terminar com um ponto e vírgula.

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

Como você pode ver esse código gera uma janela com 640 de largura por 480 pixels de altura, e em seguida começa a desenhar circulos brancos na posição do mouse. Quando o mouse é clicado, a cor do circulo muda para preto.

<img src="http://p5js.org/img/get-started/first-sketch2.png" alt="" style="margin: 0 auto;"/>

Existem duas funções principais que você ira usar. O bloco setup() é executado apenas uma vez, e é tipicamente usado para inicialização, ou para criar um progama que não precisa de um código rodando repetidamente. O bloco draw() é executado repetidamente, ele é usado para animação.

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

Por default, o drawing canvas tem tamanho 100x100. Se você quiser colocar um tamanho customizado, use a função

```javascript
  createCanvas()
```

Uma boa é sempre fazer isso na primeira linha do setup(). O código abaixo seta o canvas para tamanho 600x400:

```javascript
  function setup() {
  createCanvas(600, 400);
  line(15, 25, 70, 90);
}
```
createCanvas() vai gerar um novo canvas para desenho no tamanho especificado e concatenado à sua página html.

Se existir outros conteúdos na body da sua página, ele irá ser adicionado no conteudo seguinte.

O canvas pode ser afetado por algum css existente na página, incluindo o default. Por exemplo, muitos browsers tem padding default perto do fim da página. Se você ta percebendo que o canvas nao esta no lugar apropiado, deve ser por isso. Para corrigir isso, você deve colocar uma tag no seu <head> assim:

```javascript
 <style> body{padding:0; margin:0;} </style>
```

<blockquote>Pronto! Agora é so ir brincando com o p5.js e testando as diversas possibilidades de facanhas que podem ser feitas com ele. Para se aprofundar no p5.js: <a href="https://p5js.org/tutorials/">p5.js</a></blockquote>


<img src="http://i.giphy.com/3XRVcFDw7O1AA.gif" alt="" style="margin: 0 auto;"/>

<h3 class="section-heading">FONTES:</h3>

<a href="https://p5js.org/tutorials/">p5.js</a>
