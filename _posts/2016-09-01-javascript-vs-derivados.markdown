---
layout:     post
title:      "Javascript vs Derivados"
subtitle:   "E ai José, topa usar só Javascript?"
date:       2016-09-01 00:00:00
author:     "Felipe Mota"
header-img: "img/2016-09-01-javascript-vs-derivados/header.png"
---
<p> O número de blibiotecas e frameworks baseados em Javascript cresce progressivamente, baseado nisso fica a questão: É realmente indispensável estes derivados ? Para ser mais claro, o que se é possível fazer com os derivados consequentemente é possível em Javascript puro, no entando de qual se é preferivel o uso ? </p>

<p> Para se chegar a uma resposta, será feita analises comparando o Javascript e dois de seus derivados. </p>

<p> Para começar, será analisado Javascript vs <a href="https://jquery.com/">jQuery</a>.</p>

```javascript
	//AJAX - JSON
	//jQuery
	$.getJSON('/my/url', function(data) {

	});
	//Javascript IE9
	var request = new XMLHttpRequest();
	request.open('GET', '/my/url', true);
	request.onload = function() {
		if (request.status >= 200 && request.status < 400){ //Sucess
			var data = JSON.parse(request.responseText);
		} else {
			//We reached our target server, but it returned an error
		}
	};
	request.send()
```

<p> Em relação a requisições AJAX é inegável a simplicidade do códico jQuery, já no código de Javascript o tratamento de erros pode ser feito de maneira própria do programador, no entanto este tem que digitar um pouco mais para obter o mesmo resultado.</p>

```javascript
	//Efeitos - hide
	//jQuery
	$(el).hide();
	//Javascript IE9
	el.style.display = 'none';
```

<p> Em relação ao efeito hide de jQuery, não se é perceptivel nenhuma grande vantagem, execto é claro a quantidade menor de caracteres digitados(13 em jQuery, 26 em JavaScript) pelo programador (Sim, nós programadores atingimos niveis de preguiça em que isso se torna uma vantagem decisiva).</p>

```javascript
	//Efeitos - show
	//jQuery
	$(el).show();
	//Javascript IE9
	el.style.display = '';
```

<p> Efeito show similar a efeito hide. </p>

```javascript
	//Elementos - append
	//jQuery
	$(parent).append(el);
	//Javascript IE9
	parent.appendChild(el);
```

<p> Método de adição de elementos de maneira dinâmica ao html, não apresenta nenhuma vantagem ao jQuery em relação ao Javascript. </p>

<p> Essas são só algumas partes que se podem ser analisadas do jQuery, mas já são suficientes para demonstrar que não é tão dificil executar recursos do jQuery em Javascript puro, os códigos apresentados até agora foram retirados do site <a href="http://youmightnotneedjquery.com"> YouMightNotNeedjQuery </a> onde há outros exemplos comparativos. </p>
<p> O próximo comparativo é Javascript vs Javascript ES6 vs <a  href="https://lodash.com"> lodash </a>. Como o lodash é uma biblioteca, para se ter uma analise mais expressiva será mostrado Javascript com e sem ES6. </p>

```javascript
	//map
	//Javascript ES6
	[1,2,3].map((n) => n*3);
	//lodash
	_.map([1, 2, 3], function(n) { return n * 3; });
	// Javascript
	var arr = [1,2,3];
	for(var e in arr) arr[e] *= 3;
```

<p> O primeiro comparativo envolve alterar cada elemento de um array de maneira igual, nesse caso dado o array [1, 2, 3] foi procurado como array resultante [3, 6, 9]. Em todos os aspectos JS com ES6 fica com vantagem entre lodash e JS sem ES6, neste primeiro comparativo já se torna perceptivel a razão de colocar ES6 a parte para se fazer a analise. </p>

```javascript
	//Coleção - percurso
	//Javascript ES6
	[1,2,3].forEach((n) => console.log(n));
	//lodash
	_([1, 2, 3]).forEach(function(n) {
		console.log(n);
	});
	// Javascript
	var arr = [1,2,3];
	for(var e in arr) console.log(arr[e]);
```

<p>O objetivo deste comparativo é simplesmente percorrer um array e exibir cada um de seus elementos, nesse caso dado o array [1, 2, 3] foi esperado como resultado a impressão no console de 1, 2, 3. Novamente JS com ES6 demonstra vantagens, e o uso de Arrow functions começa a  ser viciante. </p>

```javascript
	//Join
	//Javascript ES6
	['a', 'b', 'c'].join('~');
	//lodash
	_.join(['a', 'b', 'c'], '~');
	// Javascript
	var arr = ['a','b','c'], res = "", nfirst = false;
	for(var e in arr){
		(nfirst)?res += '~': nfirst = true;
		res += arr[e];
	}
```
<p> O objetivo era dado um array de strings, retornar uma string que deveria ser o resultado da concatenação de cada string no array, tendo um separador entre cada string do array na concatenação. Neste caso não muita diferença entre o lodash e o JS com ES6, mas em relação ao JS sem ES6 a direferença é claro, ainda mais que como se obterá o resultado poderá variar de progamador para programador.</p>

<p> Em analise final, fica evidente que não é tão complexo fazer o que se é possível com frameworks e bibliotecas utilizando JS, tendo casos em que se é até vantajoso utilizar apenas JS, no entanto em questão de simplicidade de código e facilidades para o programador, fazer tudo com JS não é viável, já que muito tempo pode ser perdido com implementações que podem ser facilmente encontradas em uma biblioteca, mas o uso correto não se pode definir, pois varia conforme o programador e a situação.</p>
