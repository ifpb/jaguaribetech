---
layout:     post
title:      "Zepto.js tamanho não é documento."
subtitle:   "Uma alternativa muito similar ao Jquery."
date:       2016-09-02 00:00:00
author:     "Alex Sandro Rodrigues Barbosa"
header-img: "img/2016-09-03-Zepto/Zepto-js-tamanho-nao-e-documento.png" 
---

<h2 class="section-heading">Zepto.Js , tamanho não é documento :)</h2>

Javascript é um linguagem bastante difundida no mundo frontend, com diversas variações e simplificações para facilitar a vida do desenvolvedor. É com esse intuíto que a librarie **Zepto.js** foi criada. Permitir o nelhor aproveitamento do tempo do desenvolvedor. Aumentar sua produtivide, descomplicando tarefas que custariam muito tempo, fazendo uso de apenas pequenos comandos dessa plataforma leve e otimizada da linguagem JavaScript.

<img src="http://zeptojs.com/logo.png" alt="" style="margin: 0 auto;"/>

Muito semelhante ao seu principal concorrente **Jquery.js** (Lider da área, vale a pena salientar :) ). Também permite interação entre **HTML, CSS e JavaScript**, manipulação de **DOM**, assim como também **Ajax**.

<h2 class="section-heading">Como obter e usar a biblioteca zepto.js</h2>

Pode ser obtido pelo site da librarie em dois arquivos:

* Em sua versão completa com comentários <a href="http://zeptojs.com/zepto.js">zepto.js v1.2.0</a>
* Em sua versão simplificada, contendo apenas o código <a href="http://zeptojs.com/zepto.min.js">zepto.min.js v1.2.0</a>

Ou ainda, execute no terminal:
  ```
      npm install zepto
  ```

Depois basta realizar sua chamada no seu documento.

  ```html
  <script src="zepto.js" charset="utf-8"></script>
  ```

Vamos ver alguns poucos exemplos de uso dessa librarie.

**$.camelCase**

Recebe como parametro uma string com hífen e transforma em camelCase. Caso já esteja em camelCase não será alterada.

  ```javascript
  $.camelCase('hello-there') //=> "helloThere"
  $.camelCase('helloThere')  //=> "helloThere"
  ```

  **size**

Recebe como parâmetro um array e devolve o número de elementos de uma coleção.

  ```javascript
    size()  ⇒ number
  ```

**On**

  Adiciona manipuladores de evento para os elementos de uma coleção. Recebe como paramentros o tipo, o seletor e a função a ser executada ou false, nesse caso é o mesmo que passar uma função que retorna false.

Esse é basicamente o protótipo da função;

```javascript
on(type, [selector], function(e){ ... })  ⇒ self
on(type, [selector], [data], function(e){ ... })  ⇒ self
on({ type: handler, type2: handler2, ... }, [selector])  ⇒ self
on({ type: handler, type2: handler2, ... }, [selector], [data])  ⇒ self
```

Exemplo de aplicação:

```javascript
    var elem = $('#content')
    // observe all clicks inside #content:
    elem.on('click', function(e){ ... })
    // observe clicks inside navigation links in #content
    elem.on('click', 'nav a', function(e){ ... })
    // all clicks inside links in the document
    $(document).on('click', 'a', function(e){ ... })
    // disable following any navigation link on the page
    $(document).on('click', 'nav a', false)
```

**$.getJSON**

```javascript
    $.getJSON(url, function(data, status, xhr){ ... })  ⇒ XMLHttpRequest
    $.getJSON(url, [data], function(data, status, xhr){ ... })  ⇒ XMLHttpRequest
```

Obter dados JSON através de solicitação GET Ajax. Este é um dos atalhos para o método $.ajax. Recebe como paramentros o endereço (URL) do arquivo e a função para consumir os dados. Como é mostrado no exemplo abaixo.

```javascript
    $.getJSON('/awesome.json', function(data){
     console.log(data)
    })
```


**Enfim**

**zepto.js** praticamente resolve muitas das necessidades dos desenvolvedores, similar ao **Jquery** e com um tamanho de arquivos bem menor, em sua versão completa por apenas 57.3k não comprimido. E em sua versão **min** com tamanho de apenas 9,6k comprimidos. Sendo esse um diferêncial para uso em dispositivos móveis. E outro diferencial, é que devido a sua construção modular, caso você não necessite de todas as funcionalidades dessa librarie, baixe apenas o que precise.
Cabe ao desenvolvedor fazer sua avalização e decidir qual melhor a cada caso.

Para mais recursos, que são muitos, visite a página do <a href="http://zeptojs.com/zepto.js">zepto.js</a>.
