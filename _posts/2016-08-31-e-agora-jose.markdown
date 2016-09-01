---
layout:     post
title:      "E agora José? Como faço para enviar meu artigo?"
subtitle:   "Saiba como estruturar o seu artigo nesse blog, vendo os detalhes de como publicar e as dicas de organização do seu conteúdo."
date:       2016-08-31 00:00:00
author:     "Luiz Carlos Chaves"
header-img: "img/2016-08-31-e-agora-jose/header.jpg"
---

Sim! Isso mesmo que você leu! Vou mostrar para vocês o que deve ser feito para enviar um artigo para o Jaguaribetech. Então, vamos lá...

<img src="http://i.giphy.com/xT0Gql3DlyJ0EeRAA0.gif" alt="" style="margin: 0 auto;"/>

Primeira coisa que tem que estar claro, é que o Jaguaribetech é um blog cujo objetivo é promover a disseminação de conhecimento sobre a linguagem Javascript.

Então, será bem-vindo qualquer artigo que puxe a sardinha para as novidades e evolução da linguagem, além de reflexões e análises críticas sobre qualquer biblioteca ou framework Javascript recentemente criado nesse efervescente e dinâmico mundo frontend.

Se quiser algum pitaco é só pedir que posso sugerir algo! Mas fique sabendo que temas como as novas funcionalidades do padrão <a href="http://www.ecma-international.org/publications/standards/Ecma-262.htm">EcmaScript</a>, ou demonstrações de caras como <a href="https://vuejs.org/">Veu.js</a>, <a href="https://facebook.github.io/react/">React.js</a> e <a href="https://angularjs.org/">Angular.js</a> são mais que boas pedidas.

Porém, é claro que você não vai poder chegar colando qualquer coisa para bagunçar o coreto, tem que ser caprichado e com o máximo possível de informações, código fonte e citação de referências. Caso o resultado fique redondinho, o artigo irá ser aprovado para publicação.

<blockquote>Mas palma, palma, não priemos cânico!</blockquote>

Mais adiante será exibido como são os detalhes de publicação, mas antes vou mostrar para vocês como é que é estruturado o Jaguaribetech e como deve ser organizar os conteúdos em seus artigos.

<h2 class="section-heading">Estrutura do Jaguaribetech</h2>

O Jaguaribetech é um blog feito usando o <a href="http://jekyllrb.com/">jekyll</a>, uma ferramenta de gerencimanto de conteúdo estático escrito em ruby, que é bastante usado como blog, além disso, ele é de fácil configuração e publicação no github através do recurso do <a href="https://pages.github.com/">github pages</a>.

Vejam que a sua estrutura de código possui vários diretórios e arquivos com finalidades específicas, contudo, a atenção nesse momento deve ser dada à pasta `_posts`.

Nele é possível procurar o arquivo deste artigo, cujo o nome é `2016-08-31-e-agora-jose.markdown`, disponível neste <a href="https://github.com/ifpb/jaguaribetech/blob/master/_posts/2016-08-31-e-agora-jose.markdown">arquivo</a>. Logo, para se criar um novo artigo o primeiro passo seria criar na pasta `_posts` um arquivo com esse formato `aaa-mm-dd-titulo-do-artigo.markdown`.

Em seguida, ao analisar o código fonte deste artigo percebe-se que no início existe o fornecimento de alguns metadados, que seguem basicamente essa estrutura:

```text
---
layout:     post
title:      "E agora José? Como faço para enviar meu artigo?"
subtitle:   "Saiba como estruturar o seu artigo nesse blog, vendo os detalhes de como publicar e as dicas de organização do seu conteúdo."
date:       2016-08-31 00:00:00
author:     "Luiz Carlos Chaves"
header-img: "img/2016-08-31-e-agora-jose/header.jpg"
---
... conteúdo do artigo
```
que deve ser seguida no seu artigo, mas com as devidas adaptações nos valores dos campos `title`, `subtitle`, `date`, `author` e `header-img`.

Também é recomendado que as imagens devam possuir ausência de restrinção autoral, e para cada artigo as suas imagens devem ser colocadas em uma pasta seguindo o formato `img/aaa-mm-dd-titulo-do-artigo/`. Quanto ao campo data ele deve transcrever o momento em que foi criado o artigo, coincidindo tal valor com o nome do arquivo.

Depois de compreender os metadados o próximo passo seria analisar o restante do conteúdo deste artigo para entender como cada declaração de estrutura é processada visualmente.

<img src="http://i.giphy.com/YhyAJUCpno53y.gif" alt="" style="margin: 0 auto;"/>

A princípio é nítido que o conteúdo do arquivo faz um mix entre sintaxes de <a href="http://programminghistorian.org/new-lesson-workflow#write-in-markdown">markdown</a> e <a href="http://www.w3.org/TR/html">html</a>, por exemplo, no início do conteúdo, nas primeiras linhas de código, para definir um simples parágrafo foi preferido utilizar o markdown, como nesse trecho que exibe o primeiro e segundo parágrafo:

```text
Sim! Isso mesmo que você leu! Vou mostrar para vocês o que deve ser feito para enviar um artigo para o Jaguaribetech. Então, vamos lá...

<img src="http://i.giphy.com/xT0Gql3DlyJ0EeRAA0.gif" alt="" style="margin: 0 auto;"/>

Primeira coisa que tem que estar claro, é que o Jaguaribetech está relacionado aos temas da linguagem Javascript. Então será bem vindo qualquer artigo que puxe a sardinha para as novidades e evolução da linguagem, além de reflexões e análises críticas sobre qualquer biblioteca ou framework Javascript recente que existe nesse efervecendo e dinâmico mundo fronend da Web.

```

já a imagem obtida do <a href="http://giphy.com/">giphy</a> foi estruturada com a tag html `<img>`. Mas, caso fosse necessário exibir alguma imagem diretamente do jekyll, bastava incluir no atributo `src` com o valor seguindo o formato:

```text
<img src="{{ site.baseurl }}/img/aaa-mm-dd-titulo-do-artigo/imagem.png" alt="">
<span class="caption text-muted">Descrição da imagem.</span>
```

Vale salientar também que nessa imagem possui outra dica...

<blockquote>Sempre que usamos imagens é importante colocar legendas, que no jekyll pode ser feito com a tag span.</blockquote>

Já para incluir anotações de código basta utilizar a seguinte estrutura:

```text
 ```javascript
    var termo1 = parseInt("1 programador")+parseInt("1 computador");
    var termo2 = parseInt("2 passos para o paraíso");
    console.log(termo1 == termo2);
 ```
```

para gerar essa visualização:

```javascript
    var termo1 = parseInt("1 programador")+parseInt("1 computador");
    var termo2 = parseInt("2 passos para o paraíso");
    console.log(termo1 == termo2);
```

Enfim, para saber maiores detalhes de como escrever artigos no jekyll, além da própria documentação da própria ferramenta em seu <a href="http://jekyllrb.com/docs/home/">site</a>, seria legal que vocês pudessem conferir o artigo <a href="">Perguntas e Respostas - Jekyll</a> e <a href="https://willianjusten.com.br/making-of-parte-1/">Making of - Parte 1</a>, ambos de Willian Justen.

<h2 class="section-heading">Sim, mas que paranauê eu faço para criar o artigo?!</h2>

Primeiro, é extremamente recomendado para a utilização do Jaguaribetech, que se faça uma cópia desse projeto para sua conta no github, até mesmo porque o projeto <a href="https://github.com/ifpb/jaguaribetech">ifpb/jaguaribetech</a> possui restrições de escrita para terceiros.

Para copiar esse projeto em sua área de repositórios do github, basta ativar o botão <i class="fa fa-code-fork" aria-hidden="true"></i> fork no canto superior à direita da página do projeto no github.

<blockquote>Perceba que esse procedimento irá criar na sua conta o repositória suaConta/jaguaribetech</blockquote>

Agora com sua cópia do Jaguaribetech disponível em seu github é que podemos criar um novo artigo.

Uma das opções de criação seria através da cópia e instalação do blog em seu computador. Para isso, execute os seguintes comandos:

```shell
$ gem install jekyll
$ git clone url_do_seu_fork_do_jaguaribetech
$ cd jaguaribetech
$ jekyll serve --watch
```

Se tudo ocorrer como esperado, será disponibilizado este endereço <a href="http://127.0.0.1:4000/jaguaribetech/">http://127.0.0.1:4000/jaguaribetech/</a> para se acessar o blog localmente.

<blockquote>Mas lembre que o ruby já deve estar instalado em seu computador, uma verificação rápida pode ser feita usando o comando `ruby -v`.</blockquote>

Porém, uma outra alternativa de criação de artigos pode ser utilizada, que seria remotamente e online por meio das opções de upload e criação de novos arquivos do próprio github.

Portanto, veja que se você seguir todas os comentários já realizados sobre as estruturos do jekyll para criar o seu artigo, supostamente você obterá êxito na criação de seu conteúdo.

Mas, caso você precise de algo mais específico, e você não consiga encontrar alguma alternativa apropriada para sua necessidade, fique tranquilo, que juntos podemos ver alguma solução para o seu problema no jekyll.

Lembrando também que, se você escolheu a primeira opção de criação de artigo, após toda a estruturação de arquivos, as mudanças devem ser enviadas para seu repositório, suaConta/jaguaribetech, através dos comandos:

```shell
$ git add -A
$ git commit -m 'comentário sobre o que foi alterado'
$ git push origin master
```
<blockquote>Pronto, parabéns!</blockquote>

<img src="http://i.giphy.com/BRjNBtOgmLweQ.gif" alt="" style="margin: 0 auto;"/>

Se você conseguiu chegar nesse ponto, supostamente, você deve estar conseguindo ver seu artigo localmente em seu computador. O próximo passo será publicá-lo no site do repositório <a href="https://github.com/ifpb/jaguaribetech">ifpb/jaguaribetech</a>.

<h2 class="section-heading">Ahhh, agora vamos publicar</h2>

Nesta última etapa, vamos ver todos os detalhes para publicar o seu artigo, que nada mais é que o processo de transferência dos commits que geraram o artigo no repositório, suaConta/jaguaribetech para o repositório original <a href="https://github.com/ifpb/jaguaribetech">ifpb/jaguaribetech</a>.

Mas é de suma importância que o artigo esteja funcionando adequadamente, pois essa transferência será testada para permitir que a integração com o <a href="https://github.com/ifpb/jaguaribetech">ifpb/jaguaribetech</a> não gere inconsistências.

A realização da cópia pode ser ativida com o processo do <a href="https://help.github.com/articles/creating-a-pull-request/">Pull Request</a>, que fica acessível através da aba `Pull requests` no github do seu repositório suaConta/jaguaribetech. Na página acessada use a opção `New pull request` para propor uma solicitação de cópia dos seus commits criados para o repositório <a href="https://github.com/ifpb/jaguaribetech">ifpb/jaguaribetech</a>.

Essa solicitação em breve será analisada, e assim que for confirmada seu artigo estará disponível no Jaguaribetech. Mas, para mais curiosidades sobre Pull Request procure ler o artigo <a href="http://blog.da2k.com.br/2015/02/04/git-e-github-do-clone-ao-pull-request/">Git e Github - Do clone ao pull request</a> de Fernando Daciuk.

<h2 class="section-heading">Conclusão</h2>

Pronto, finalmente chegou a hora de apagar as velinhas e de cantar a música We are the champions do Queen.

Espero que todos tenham gostado do tutorial disfarçado de artigo, que possuiu como objetivo principal ajudar a vida de todos que irão publicar no Jaguaribetech.

Não esqueçam que qualquer dúvida pode mandar as ordens, e que venham os artigos!

<img src="http://i.giphy.com/BjQTWPEVZjM6Q.gif" alt="" style="margin: 0 auto;"/>
