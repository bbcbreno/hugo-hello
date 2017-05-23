+++
date = "2017-05-20T22:35:36-03:00"
lastmod = "2017-05-21T22:35:36-03:00"
draft = false
title = "Uma introducao ao JavaScript ES6"
euzin = "xpto"

[blackfriday]
  angledQuotes = true
  fractions = false
  plainIDAnchors = true
  extensions = ["hardLineBreak"]

+++

Vamos utilizar:
+ JavaScript (JS)
+ ECMAScript6 (ES6)
+ Node
+ Babel
+ WebPack

Propósito do JavaScript.

A JavaScript nasceu para que o programador possa criar alguns scripts que serão executados diretamente no navegador do cliente, antes de passar pelo servidor da aplicação. Um exemplo simples: o usuário preencher algum formulário de cadastro e o CPF inválido, antes do usuário enviar o formulário para o servidor efetuar o cadastro, o navegador pode executar um código JavaScript e este alertar o usuário de que o CPF está inválido. Assim, o usuário não precisará recarregar a página toda para saber que o CPF estava errado, poupando tempo e melhorando a usabilidade do usuário.

Propósito do ECMASciprt (atualmente na 6, tá saindo a 7 e em breve a 8).

O JavaScript é uma linguagem antiga, criada em 1995 e para resolver um problema bem simples. Porém, o uso do JavaScript evoluiu bastante com as páginas tonarnando cada mais mais dinâmicas e complexas: chat, lista de amigos, feed de notícias, notificações e etc numa única página, cada um desses componentes fazendo requisições e alterando seus status na mesma hora, tudo se deve ao JavaScript. Por conta de toda essa complexidade, a comunidade deu aquele tapa no JS trazendo estruturas e recursos de programação mais modernos, como a orientação a objeto. E este é o objetivo desse artigo, explicar algumas características do ES6.

O JS deu um passo importante: hoje temos JS rodando em servidores também, através do Node.

Propósito do Node

O Node é um servidor em JS para podermos desenvolver servidores facilmente escaláveis.

Propósito do Babel

O nosso navegador interpreta apenas JS (alguns navegadores mais modernos consegue interpreta ES6, mas ainda n é regra). O Babel é um transpiler, ou seja, ele irá pegar todo o nosso código escrito em ES6 e converter para um código JS que o navegador irá entender.

Propósito do WebPack

Configurando o ambiente

Após instalação do Node (https://nodejs.org/en/) vamos criar uma nova pasta chamada hello-es6, iniciar e configurar um novo projeto Node:

> mkdir hello-es6
> cd hello-es6
> npm init -y
> npm install --save-dev webpack

Vamos criar nosso index.html.

/build/index.html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello ES6</title>
  </head>
  <body>
    <script type="text/javascript" src="bundle.js"></script>
  </body>
</html>

Vamos criar nosso arquivo JS.
/app/index.js
console.log("Hello JS")

Configurando nosso Webpack. Este arquivo é responsável em pegar nossos arquivos JS (atualmente existe apenas o app/index.js), empacotar tudo no arquivo bundle.js e colocar dentro da pasta build.

/webpack.config.js
module.exports = {
  entry: ['./app/index.js'],
  output: {
    path: './build',
    filename: 'bundle.js'
  }
}

Feito isto precisamos atualizar nossos sciprts do Node. Este script irá executar quando digitarmos ele no terminal (faremos isto logo mais). Abra o package.json e altere apenas a sessão "scripts", mantenha o resto como esta.

/package.json
...
"scripts": {
  "build": "webpack"
}
...

No terminal rode:

> npm run build

<ul class="task-list">
<li><input type="checkbox" disabled="" class="task-list-item"> a task list item</li>
<li><input type="checkbox" disabled="" class="task-list-item"> list syntax required</li>
<li><input type="checkbox" disabled="" class="task-list-item"> incomplete</li>
<li><input type="checkbox" checked="" disabled="" class="task-list-item"> completed</li>
</ul>
