---
layout:     post
title:      "Usando Angular Chart"
subtitle:   "Saiba com criar gráficos usando Angular Chart"
date:       2016-09-01 00:00:00
author:     "José Raimundo Barbosa"
header-img: "img/2016-09-01-usando-angular-chart/chart_div.jpg"
---



<h2 class="section-heading">Onde utilizar gráficos?</h2>

Gráficos representam ótimas ferramentes para representar dados numéricos, com uma aparência mais agradável e compreensível. Há diversas formas de gráficos além de mesclagem entre eles, o que proporciona um imenso leque de alternativas de acordo com a necessidade do usuário.

Em praticamente tudo, todas sequências de dados números com algum tipo de relação entre si, podem ser apresentados em forma de gráficos. As diversas variações de gráficos amplia o uso para diversas situações como por exemplo: grupos, variação, desempenho, comparação, especificação e etc.


<h2 class="section-heading">Angular Chart</h2>


<a href="https://angularjs.org/">AngularJS</a>  é um framework JavaScript open-source gerenciado pelo Google, seus diversos módulos possibilitam desenvolver aplicações web diversas. Neste artigo, será apresentado o módulo chart que foi desnvolvido com base no <a href="http://www.chartjs.org/">ChartJS</a> , ele oferece diversos gráficos responsivos, detalhados e de fácil implementação.
<img src="https://www.safaribooksonline.com/blog/wp-content/uploads/2013/11/fig1.ng-chartjs-banner.jpg" alt="" style="margin: 0 auto;"/>


As vantagens de utilizar AngularJS Chat em vez do ChatJS diretamente, se resumem em facilidade de uso, uma vez que o Angular apresentam uma API simplificada para uso da biblioteca chat.js.


<h2 class="section-heading">Instalação</h2>


Para utilizar o AngularJS Chart é necessário instalar suas duas dependências: AngularJS (versão >= 1.2.x) e Chart.js (versão >= Chart.js 2.0.x).

Links para dependências:
<li><a href="https://angularjs.org/">angular.js</a></li>
<li><a href="http://www.chartjs.org/">chart.js</a></li>

Após isso, baixe o arquivo .js com o comando:


```shell
$ npm install angular-chart.js --save
```
<blockquote>Também disponível em: https://github.com/jtblin/angular-chart.js</blockquote>


Pronto, agora só precisa incluir o Angular Chart no seu site:

```text
<script src="node_modules/chart.js/Chart.min.js"></script>
<script src="node_modules/angular-chart.js/dist/angular-chart.min.js"></script>
```

<h2 class="section-heading">Exemplo de uso</h2>

Para criar um gráfico, por exemplo, de linhas, basta chamar no <I>html</I> o tipo de gráfico desejado, e adaptar as suas características e valores.


<blockquote>Exemplo de código HTML</blockquote>

```code
<canvas id="line" class="chart chart-line" chart-data="data"
chart-labels="labels" chart-series="series" chart-options="options"
chart-dataset-override="datasetOverride" chart-click="onClick"
</canvas>
```

O exemplo a seguir, apresenta um gráfico de linhas referente a distribuição de valores entre os meses, note que também é possível inserir componentes como legendas e pontos autoexplicativos ou expositivos.

<img src="http://angularscript.com/wp-content/uploads/2014/11/angular-chart.js-Reactive-Chart.jpg" alt="" style="margin: 0 auto;"/>


Para modificar os valores, você deve utilizar as funções de acordo com o gráfico selecionado.
<blockquote>Exemplo de código JavaScript</blockquote>

```code
angular.module("app", ["chart.js"]).controller("LineCtrl", function ($scope) {

  $scope.labels = ["January", "February", "March", "April", "May", "June", "July"];
  $scope.series = ['Series A', 'Series B'];
  $scope.data = [
    [65, 59, 80, 81, 56, 55, 40],
    [28, 48, 40, 19, 86, 27, 90]
  ];
  $scope.onClick = function (points, evt) {
    console.log(points, evt);
  };
  $scope.datasetOverride = [{ yAxisID: 'y-axis-1' }, { yAxisID: 'y-axis-2' }];
  $scope.options = {
    scales: {
      yAxes: [
        {
          id: 'y-axis-1',
          type: 'linear',
          display: true,
          position: 'left'
        },
        {
          id: 'y-axis-2',
          type: 'linear',
          display: true,
          position: 'right'
        }
      ]
    }
  };
});
```


Por último, basta modificar a aparência usando CSS, de acordo com suas preferências.
<blockquote>Exemplo de código CSS</blockquote>


```code
(function (ChartJsProvider) {
  ChartJsProvider.setOptions({ colors : [ '#803690', '#00ADF9', '#DCDCDC', '#46BFBD', '#FDB45C', '#949FB1', '#4D5360'] });
});
```




Além dos gráficos convencionais, você também terá funcionalidades como:
<li>Gráficos dinâmicos: Excelentes para representar dados de fontes contínuas. </li>
<li> Gráficos interativos: Em que o usuário pode interagir e presenciar as variações de acordo com a alteração dos valores.</li>


<img src="http://www.lobaedesign.com/wp-content/uploads/2013/10/chart-js-example.jpg" alt="" style="margin: 0 auto;"/>



<h2 class="section-heading">Conclusão</h2>

Usando Angular Chart, você poderá explicar seus resultados, análises e demais valores, de maneira compreensível e agradável, livrando seus clientes e navegantes do esforço de interpretar variações quantidades assustadoras de dados disponibilizados em tabelas.

<h2 class="section-heading">Fontes</h2>

<li><a href="http://jtblin.github.io/angular-chart.js/">http://jtblin.github.io/angular-chart.js/</a></li>
<li><a href="http://www.chartjs.org/">http://www.chartjs.org/</a></li>
