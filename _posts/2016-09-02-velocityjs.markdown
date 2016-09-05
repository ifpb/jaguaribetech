---
layout:     post
title:      "Velocity"
subtitle:   "Conheça a mais popular biblioteca de JS de animação web open source"
date:       2016-09-02 00:00:00
author:     "Felipe Medeiros Alves"
header-img: "img/2016-09-02-velocityjs/monument-valley.jpg"
---

Velocity é uma biblioteca JavaScript projetada para simplificar a criação de scripts do lado do cliente da animação website. A Sintaxe é projetada para tornar mais fácil para criar animações complexas para HTML e elementos SVG.

Além de seus benefícios de fluxo de trabalho, ela proporciona um desempenho de animação que é competitivo com animação baseada em CSS. Seu desempenho se dá através da manutenção de um cache interno de estados de animação e da diminuição do "layout thrashing", o comportamento indesejável que navegadores web sofrem quando, visualmente, atualizam em um ritmo rápido.

No todo, seus benefícios de fluxo de trabalho e desempenho permitem ser usada para a programação de animação sofisticada, que pode ser integrada nas aplicações web e móveis. Seu amplo suporte à navegadores e dispositivos tornam ideal para distribuições de grandes empresas que devem suportar dispositivos de baixa potência.

<h2 class="section-heading">Características</h2>

Características da biblioteca incluem:

  - janela do navegador e elemento de rolagem
  - independência do jQuery
  - reversão de animação (a capacidade de desfazer a animação anterior) e looping de animação
  - elemento de animação SVG
  - RGB e hex da animação da cor

  Velocity suporta todos os principais navegadores de desktop ( Firefox , Google Chrome e Safari ), mais os iOS e Android sistemas operacionais móveis. O seu apoio se estende tanto para trás como o Internet Explorer 8 e Android 2.3.

<h2 class="section-heading">Incluindo a biblioteca</h2>

  A biblioteca Velocity é um único arquivo JavaScript que contém todas as suas funções essenciais. Ele pode ser incluído dentro de uma página web, ligando para uma cópia local ou para uma das muitas cópias disponíveis a partir de servidores públicos, incluindo MaxCDN, jsDelivr ou Cloudflare CDNjs.

```text

    < Roteiro  src = "velocity.min.js" > </ script de >

```

<blockquote>Também é possível incluir diretamente de redes de distribuição de conteúdo. (O link começando com // é o protocolo URL relativo.)</blockquote>

```text

    < Roteiro  src = "//cdn.jsdelivr.net/velocity/1.2.3/velocity.min.js" > </ script de >

```

<h2 class="section-heading">Estilos de utilização</h2>

Velocity tem dois estilos de uso:

  A `$.Velocity` função, que é um método de fábrica se estendia desde o jQuery objeto raiz. Este método anima matérias- DOM elementos em vez de jQuery elementos -wrapped. Este é o estilo empregado pelo uso da Velocity sem jQuery na página.
  A `$element.velocity()` função. Este é o estilo usado para animar objetos elemento jQuery quando jQuery está presente na página.

Chamadas de animação consistem em fornecer o(s) elemento(s) desejado(s) para animar, um mapa da propriedade de animação para especificar as propriedades CSS a serem animadas, e um objeto opcional de opções para especificar configurações de animação (por exemplo, duração ).

<h2 class="section-heading">Argumentos</h2>

A função aceita um ou mais argumentos. O primeiro argumento, que é obrigatório, pode ser o nome de um comando pré-definido (por exemplo, de deslocamento ou reverter ) ou um objeto contendo propriedades CSS a serem animadas:

```text

// Animar largura de um elemento para 100px e sua propriedade esquerda para 200px
$elemento.Velocidade({  width :  "100px" ,  deixou :  "200px"  });

```

O segundo argumento, que é opcional, é um objeto. Ele é usado para especificar opções de animação, tais como duração , flexibilização e completa (uma função arbitrária para executar uma vez que a animação foi concluída):

```text

$ elemento
    . velocidade ({  altura :  300  },  {  duração :  1000  })
    // Continue para esta animação, uma vez que a anterior foi concluída
    . velocidade ({  superior :  200  },  {  duração :  600  })
   // E mais uma vez ...
    . velocidade ({  opacidade :  0  },  {  duração :  200  });

```
