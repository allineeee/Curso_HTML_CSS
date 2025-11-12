## Curso CSS3

- css tem especificidade, alguns estilos podem sobrescrever outros, no caso o azul sobrescreve o vermelho, e o id tem especificidade forte, então a classe não sobrescreve ele:
```html
    <style>
        h1 {
            background: red;
        }

        h1 {
            background: blue;
        }
        #cabecalho-dois{
            background: green;
        }
        .fundo-vermelho{
            background: red;
        }
    </style>
```
- o '#' é usado pra ids e o '.' para classes
- no caso abaixo, a margin bottom do primeiro elemento, não é somada com a margi-top do segundo elemento, é usado a maior margin. Como nesse caso ambas as margins tem o mesmo tamanho, fica uma diferença de 20px entre os dois elementos
```css
  .section-one {
            width: 200px;
            height: 50px;
            background-color: deeppink;
            background-image: url(https://www.aaronreedphotography.com/images/xl/Sweet-Dreams-2022.jpg);
            background-size: cover;
            background-position: center center;
            border: 5px solid blue;
            padding: 15px;
            color: white;
            margin: 20px;
        }

        .section-two {
            background: cyan;
            width: 200px;
            height: 50px;
            border: 5px solid;
            padding: 15px;
            margin: 20px;
        }
```

## Pesquisar mais
- seletores (.,*, #)???
- quais são os seletores do css???
- box model, box-sizing: border-box;
- display: block;
- a tag style pode ficar em qualquer lugar no html??
-```<link rel="stylesheet" href="style.css">```
- seleção de descendente
- elementos com duas classes "pai filha"
```html
    <!-- nesse caso, a div filha herda as 
     configurações da div pai -->
    <div class="pai">
        Pai
        <div class="filha">
            Filha
        </div>
    </div>
```

```css
div {
    color: initial;
    margin-left: 20px;
}

.pai > .filha{
    color: blue;
}
```
```html
    <div class="pai">
        Pai
        <div class="filha outra qualquer">
            Filha 1
            <div class="filha outra qualquer">
                Filha da filha
            </div>
        </div>
        <div class="filha outra qualquer">
            Filha 2
            <div class="filha outra qualquer">
                Filha da filha 2
            </div>
        </div>
    </div>
```
- seletore de atributo etc:
```css
.pai h1+p{
    color: red;
}

.pai p+h1{
    color: yellow;
}

.pai h1~p{
    color: yellow;
}

[meu-atributo]{
    color: blue;
}

[meu-atributo="valor"]{
    color: blue;
}

[meu-atributo~="valor"]{
    color: blue;
}

[meu-atributo|="valor"]{
    color: blue;
}

[meu-atributo^="valor"]{
    color: blue;
}

[meu-atributo$="valor"]{
    color: blue;
}

[meu-atributo*="valor"]{
    color: blue;
}


```

- seletores de pseudoclasses: hover...
- links que foram visitados e links que não foram visitados (a:link, a:visited)
- li:last-child, input:checked +p,
- seletor not:
```css
input:checked + p{
    color: red;
}

input:not(:checked) + p{
    background: yellowgreen;
}

p:not(.meio){
    color: blue;
}
```

```css
ul li:nth-child(odd) {
    background-color: rebeccapurple;
}

ul li:nth-child(even) {
    background-color: darkturquoise;
}

ul li:nth-child(3n) {
    background-color: deeppink;
}

ul li:nth-child(3n + 5) {
    background-color: yellow;
}
```
- pseudo elemento:
```css
ul li::after{
    content: " - ";
}

p::first-letter{
    font-size: 150px;
    display: block;
    float: left;
    margin: 0 20px 20px 0;
    color: red;
}

p::selection{
    background-color: black;
    color: #fff;
}

```

- especificidade no css (como faz a conta 1, 1, 0) e !important
- https://specificity.keegan.st/
- herança no css
- unidade de medidas no css: %, auto, max, min, em
- max-widht, min-width, height, view port
- propriedade  (inline, block, flex, grid), clear: both
- propriedade float???
- box-sizing: border-box;
- cores no css: hexadecimal vernelho(FF) verde(FF) azul(FF), #abc123; - ABCDEF123456789
- pq o vermelho é #ff0000 e não #990000
- rgb e rgba
- hsl e hsla
- unidades de medida: unidades absolutas, unidades relativas, em (elemento pai multiplicação), rem (elemento root), vw, vh
- https://www.w3schools.com/cssref/css_units.php
- links de ancoras
- propriedades pra trabalhar com textos:
```css
p{
    /* color: red;
    background-color: yellow;
    font-style: italic;
    font-weight: bold;
    direction: rtl;
    letter-spacing: 1px;
    text-decoration: overline;
    word-spacing: 5px;
    text-indent: 50px;
    text-shadow: 2px 2px red;
    line-height: 30px; */
    text-align: left;
    font-size: 20px;  
}
```

- position: absolute, fixed, sticky..., z-index
- media queries com exemplos
- https://developer.mozilla.org/pt-BR/docs/Web/CSS/Guides/Media_queries/Using
- flexbox (eixo principal, eixo perpendicular, align content, align items, justify content, cross start, cross axis, cross end, flex flow, flex grow)
- display: grid???
- rever aulas:
- 08:12:25 - Entenda o Flexbox
- 08:55:46 - Entenda CSS Grid
- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://youtu.be/uHiSYokteNY?si=kGm4lEusCUBTHuff
- https://youtu.be/odYCJU6NHss?si=jl4YplC_dlWtTzuR
- criar variaveis no css - :root{--primary-color: #0a1128;}
- inherit é herança????
- criar contador no css???
- pq tem content: ''; no pseudo???