Este projeto é um slideshow simples e eficiente, construído apenas com HTML, CSS e JavaScript puro.
A proposta é treinar manipulação de DOM, movimentação de elementos e lógica de navegação entre imagens sem depender de bibliotecas externas.

 Como funciona

As imagens são carregadas dinamicamente a partir de um array:

const images = [
    { id: '1', url: './img/2.jpg' },
    { id: '2', url: './img/3.jpg' },
    ...
];


O conteúdo é inserido dentro do contêiner:

<div class="container-items" id="container-items"></div>


As setas de navegação controlam a ordem dos elementos:

Previous («)
Move o primeiro item para o final.

Next (»)
Move o último item para o início.

Esse rearranjo de elementos cria o efeito de slideshow sem precisar alterar índices ou usar carrosséis prontos.

 Lógica principal

O ponto central do efeito está nessas duas funções:

Ir para a próxima imagem:
const previous = () => {
    containerItems.appendChild(items[0]);
    items = document.querySelectorAll('.item');
};

Voltar para a imagem anterior:
const next = () => {
    const lastItem = items[items.length - 1];
    containerItems.insertBefore(lastItem, items[0]);
    items = document.querySelectorAll('.item');
};


A lógica é simples, mas inteligente:

Não mexe com índices

Não recria elementos

Só reorganiza nós DOM

É performático e limpo

 Estilo e Interface

O layout segue uma linha minimalista e funcional:

Slideshow centralizado na tela

Fundo escuro para destacar as imagens

Botões laterais com hover chamativo

Imagens com borda arredondada e transição suave

O visual combina bem com imagens de destaque e dá sensação de movimento mesmo com código simples.

 Estrutura de arquivos
/
│ index.html
│ style.css
│ slideShow.js
└── img/
     ├── 2.jpg
     ├── 3.jpg
     ├── 4.jpg
     ├── 5.jpg
     ├── 6.jpg
     ├── 7.jpg
     └── fundo.jpg

 Objetivo do Projeto

Esse slideshow é útil para treinar:

Manipulação direta de elementos DOM

Criação dinâmica de conteúdo com JavaScript

Movimentação de elementos sem usar sliders prontos

Lógica de navegação simples e escalável

Construção de UI com CSS responsivo
