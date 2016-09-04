---
layout:     post
title:      "Maps JavaScript API"
subtitle:   "Saiba o que é e como usar a API do google maps"
date:       2016-08-03 00:21:32
author:     "Rena Matias Mendes"
header-img: "img/2016-09-03-Maps-JavaScript-API/googlemaps.jpg"
---
Esta artigo foi projetado para permitir que você comece rapidamente a explorar e desenvolver aplicativos com a Google Maps API. Acesse a referência da Google Maps API (https://developers.google.com/maps/documentation/javascript/3.exp/reference?hl=pt-br).


A maneira mais fácil de começar a aprender sobre a Google Maps API é ver um exemplo simples. A página a seguir exibe um mapa centralizado em Sidnei, New South Wales, Austrália:

```javascript

<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      html, body { height: 100%; margin: 0; padding: 0; }
      #map { height: 100%; }
    </style>
  </head>
  <body>
    <div id="map"></div>
    <script type="text/javascript">

var map;
function initMap() {
  map = new google.maps.Map(document.getElementById('map'), {
    center: {lat: -34.397, lng: 150.644},
    zoom: 8
  });
}

    </script>
    <script async defer
      src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
    </script>
  </body>
</html>

```

-Declarar o aplicativo como HTML5

Recomenda-se declarar um DOCTYPE verdadeiro no aplicativo web. Nestes exemplos, declaramos nossos aplicativos como HTML5 usando o DOCTYPE simples do HTML5, mostrado a seguir:

```javascript
<!DOCTYPE html>
```

A maioria dos navegadores atuais renderiza o conteúdo declarado com esse DOCTYPE no "modo padrão", o que significa que o aplicativo deve ter maior compatibilidade em diversos navegadores. O DOCTYPE também é projetado para degradar de forma organizada. Esse recurso é ignorado por navegadores que não o entendem e usam o "modo quirks" para exibir o conteúdo.

Observe que há código CSS que funciona no modo quirks, mas não é válido no modo padrão. Especificamente, todos os tamanhos baseados em porcentagem devem herdar elementos de bloco pai e, se um dos ancestrais não especificar um tamanho, supõe-se que o tamanho seja 0 x 0 pixels. Por esse motivo, incluímos a declaração <style> a seguir:

```javascript
<style type="text/css">
  html, body { height: 100%; margin: 0; padding: 0; }
  #map { height: 100%; }
</style>
```

Essa declaração CSS indica que o contêiner do mapa <div> (com id map) ocupa 100% da altura do corpo HTML. Observe que devemos declarar especificamente essas porcentagens para <body> e também para <html>.

-Carregar a Google Maps API

```javascript
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
</script>
```
O URL contido na tag script é a localização de um arquivo JavaScript que carrega todos os símbolos e as definições necessários para usar a Google Maps API. Essa tag script é obrigatória.

O atributo async permite que o navegador renderize o restante do site durante o carregamento da Maps API. Quando a API está pronta, ela chama a função especificada usando o parâmetro callback.

O parâmetro key contém a chave de API do aplicativo. Consulte https://developers.google.com/maps/documentation/javascript/get-api-key?hl=pt-br para obter mais informações.

-HTTPS ou HTTP

Consideramos a segurança na web muito importante e recomendamos usar HTTPS sempre que possível. Como parte de nossos esforços para tornar a web mais segura, disponibilizamos todas as Google Maps APIs sobre HTTPS. O uso da criptografia HTTPS torna o site mais seguro e mais resistente a invasões ou adulterações.
Recomendamos carregar a Google Maps JavaScript API sobre HTTPS usando a tag <script> fornecida acima.
Se necessário, carregue a Google Maps JavaScript API sobre HTTP solicitando http://maps.googleapis.com/ ou http://maps.google.cn para usuários na China.

-Bibliotecas

Durante o carregamento da JavaScript Maps API no URL, você pode carregar bibliotecas adicionais usando o parâmetro de URL libraries. As bibliotecas são módulos de código que oferecem funcionalidade adicional à JavaScript API principal e somente são carregadas mediante solicitação explícita. Para obter mais informações, consulte https://developers.google.com/maps/documentation/javascript/libraries?hl=pt-br.

-Carregamento síncrono da API

Na tag script que carrega a Maps API, é possível omitir o atributo async e o parâmetro callback. Essa ação bloqueia o carregamento da API até que seu download seja concluído.
Como resultado, o carregamento da página provavelmente será mais lento. Por outro lado, isso significa que é possível escrever as tags de script subsequentes supondo que a API já está carregada.

-Elementos de DOM do mapa

```javascript
<div id="map"></div>
```
Para que o mapa seja exibido em uma página, é necessário reservar um lugar para ele. Normalmente, isso é feito criando um elemento div nomeado e obtendo uma referência para esse elemento no modelo de objetos do documento (DOM) do navegador.
No exemplo acima, usamos CSS para definir a altura do div do mapa para "100%". O mapa se expande de acordo com o tamanho dos dispositivos móveis. Pode ser necessário ajustar os valores de largura e altura com base no tamanho da tela e no preenchimento do navegador. Observe que os divs normalmente herdam a largura de seu elemento contêiner. Divs vazios normalmente têm a altura 0. Por esse motivo, sempre defina explicitamente uma altura no <div>.

-Opções do mapa

Há duas opções obrigatórias para cada mapa: center e zoom.

```javascript
map = new google.maps.Map(document.getElementById('map'), {
  center: {lat: -34.397, lng: 150.644},
  zoom: 8
});
```

-Níveis de zoom

A resolução inicial para exibir o mapa é definida pela propriedade zoom, com zoom 0 correspondendo a um mapa do planeta com o zoom mais distante possível, e níveis mais altos de zoom aumentando a resolução da exibição do mapa.
```javascript
zoom: 8
```
A disponibilização de um mapa de todo o planeta como uma única imagem exigiria um mapa imenso ou um mapa pequeno com resolução muito baixa. Como resultado, as imagens de mapa no Google Maps e na Maps API são divididas em "blocos" de mapa e "níveis de zoom". Em níveis baixos de zoom, um pequeno conjunto de blocos de mapa cobre uma grande área. Em níveis de zoom mais altos, os blocos têm maior resolução e cobrem uma área menor.

As três imagens a seguir refletem a mesma localização de Tóquio, nos níveis de zoom 0, 7 e 18.



Para obter informações sobre como a Maps API carrega blocos de acordo com o nível de zoom atual, consulte https://developers.google.com/maps/documentation/javascript/maptypes?hl=pt-br#TileCoordinates na documentação dos tipos de mapa.

-O objeto Map
``` javascript
map = new google.maps.Map(document.getElementById("map"), {...});
```
A classe JavaScript que representa um mapa é a classe Map. Os objetos dessa classe definem um único mapa na página. (É possível criar mais de uma instância dessa classe. Cada objeto define um mapa separado na página.) Criamos uma nova instância dessa classe usando o operador JavaScript new.

Ao criar uma nova instância de mapa, especifique um elemento HTML <div> na página como contêiner para o mapa. Os nós HTML são filhos do objeto JavaScript document. A referência a esse elemento é obtida por meio do método document.getElementById().

Esse código define uma variável (denominada map) e atribui essa variável a um novo objeto Map. A função Map() é conhecida como um construtor que cria um novo mapa dentro do contêiner HTML informado (normalmente, um elemento DIV) usando os parâmetros (opcionais) passados.

Se o código não funciona:

-Procure erros de digitação.
-Lembre-se de que a linguagem JavaScript diferencia maiúsculas de minúsculas.
-Verifique os elementos básicos.Alguns dos problemas mais comuns ocorrem na criação inicial do mapa. Por exemplo:
    *Confirme se as propriedades zoom e center, nas opções do mapa, foram especificadas.
    *Verifique se foi declarado um elemento div no qual o mapa será exibido na tela.
    *Verifique se o elemento div para o mapa tem uma altura. Por padrão, os elementos div são criados com uma altura de 0, o que os torna invisíveis.
-Consulte nossos exemplos para obter uma implementação de referência (https://developers.google.com/maps/documentation/javascript/examples/map-simple?hl=pt-br).
    *Use um depurador JavaScript para ajudar a identificar problemas, como o depurador disponível em https://developers.google.com/web/tools/chrome-devtools/debug/?utm_source=dcc&utm_medium=redirect&utm_campaign=2016q3.Comece verificando a existência de erros no console JavaScript.
    *Publique dúvidas no Stack Overflow(https://stackoverflow.com/users/login?ssrc=anon_ask&returnurl=https%3a%2f%2fstackoverflow.com%2fquestions%2fask%3ftags%3dgoogle-maps-api-3%2cgoogle-maps). A página Support (https://developers.google.com/maps/support/?hl=pt-br) oferece diretrizes sobre a melhor maneira de publicar dúvidas.
