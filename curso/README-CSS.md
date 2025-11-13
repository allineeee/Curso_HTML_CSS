## Curso CSS3

### Teoria

- CSS tem especificidade (ordem de prioridade), alguns estilos podem sobrescrever outros
- Quando vários seletores afetam o mesmo elemento, o navegador usa uma ordem de prioridade:
  1. `!important` → prioridade máxima
  2. Estilo inline (`style="..."`)
  3. ID (`#id`)
  4. Classe, pseudo-classes e atributos (`.classe`, `:hover`, `[attr]`)
  5. Tag (elemento) (`div`, `p`, `h1`)
  6. Herança e valores padrão
- A "conta de especificidade" é representada como (IDs, Classes, Elementos):
  ```css
  #cabecalho { } /* (1,0,0) */
  .fundo-vermelho { } /* (0,1,0) */
  h1 { } /* (0,0,1) */
  ```
- Calcular especificidade: https://specificity.keegan.st/

### Seletores básicos

| Tipo            | Exemplo   | Descrição                                   |
| --------------- | --------- | ------------------------------------------- |
| Universal       | `*`       | Seleciona todos os elementos                |
| Tag             | `p`       | Seleciona todas as tags `<p>`               |
| Classe          | `.classe` | Seleciona elementos com a classe            |
| ID              | `#id`     | Seleciona elemento com o ID específico      |
| Descendente     | `div p`   | Seleciona `<p>` **dentro** de `<div>`       |
| Filho direto    | `div > p` | Seleciona `<p>` **filho direto** de `<div>` |
| Irmão adjacente | `h1 + p`  | Seleciona `<p>` **logo após** um `<h1>`     |
| Irmãos gerais   | `h1 ~ p`  | Seleciona **todos** os `<p>` após `<h1>`    |

```css
div {
    color: initial;
    margin-left: 20px;
}

.pai > .filha{
    color: blue;
}
```

### Seletores de atributo

```css
/* tem o atributo */
[meu-atributo]{
    color: blue;
}

/* atributo igual ao carro */
[meu-atributo="carro"]{
    color: blue;
}

/* contém "carro" na lista que é separada por espaço */
[meu-atributo~="carro"]{
    color: blue;
}

/*  */
[meu-atributo|="carro"]{
    color: blue;
}

/* valor começa com "carro" */
[meu-atributo^="carro"]{
    color: blue;
}

/* valor termina com "carro" */
[meu-atributo$="carro"]{
    color: blue;
}

/* valor contém "carro" */
[meu-atributo*="carro"]{
    color: blue;
}
```

###  Pseudo-classes

- Representam estados especiais de um elemento.

| Pseudo-classe  | Exemplo             | Descrição                                               |
| -------------- | ------------------- | ------------------------------------------------------- |
| `:hover`       | `a:hover`           | Quando o mouse está sobre o link                        |
| `:active`      | `button:active`     | Enquanto está sendo clicado                             |
| `:visited`     | `a:visited`         | Link já visitado                                        |
| `:focus`       | `input:focus`       | Campo de formulário ativo                               |
| `:checked`     | `input:checked`     | Checkbox selecionado                                    |
| `:not()`       | `p:not(.meio)`      | Seleciona elementos que **não** correspondem ao seletor |
| `:nth-child()` | `li:nth-child(odd)` | Elemento na posição N                                   |
| `:last-child`  | `li:last-child`     | Último elemento filho                                   |

- `odd` = ímpar | `even` = par | `3n + 2` = padrão matemático

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

/* colore de 3 em 3 */
ul li:nth-child(3n) {
    background-color: deeppink;
}

/* colore de 3 em 3, mas a partir do 5º elemento */
ul li:nth-child(3n + 5) {
    background-color: yellow;
}
```

### Pseudo-elementos

- Afetam partes específicas de um elemento.

| Pseudo-elemento  | Exemplo           | Descrição                   |
| ---------------- | ----------------- | --------------------------- |
| `::before`       | `p::before`       | Insere conteúdo **antes**   |
| `::after`        | `p::after`        | Insere conteúdo **depois**  |
| `::first-letter` | `p::first-letter` | Primeira letra              |
| `::first-line`   | `p::first-line`   | Primeira linha              |
| `::selection`    | `::selection`     | Área selecionada pelo mouse |

- Exemplo:

```css
p::after {
  content: " — fim do texto";
}
p::selection {
  background: black;
  color: white;
}
```

- `content: ' '` é obrigatório para gerar o pseudo-elemento, mesmo vazio (serve para criar formas, ícones ou efeitos visuais).


### Box Model

- O box model define como o espaço do elemento é calculado:

```
+----------------------+
|      margin          |  ← externo
|  +----------------+  |
|  |    border      |  |
|  | +------------+ |  |
|  | |  padding   | |  | ← interno
|  | +------------+ |  |
|  +----------------+  |
+----------------------+
```

- `padding`: espaçamento interno (dentro da borda). Não pode ser negativo.
- `margin`: espaçamento externo. Pode ser negativo.
- `box-sizing`: como o tamanho total é calculado. O `border-box` inclui padding e borda no cálculo de largura/altura (`box-sizing: border-box`).
- Ordem dos valores: Top → Right → Bottom → Left (sentido horário)
- Valores do padding/margin:
    - 1 valor -> aplica em todos os lados
    - 2 valores -> (top/bottom) (left/right)
    - 3 valores -> (top) (left/right) (bottom)
    - 4 valores -> (top) (right) (bottom) (left)

```css
padding: 10px;
padding: 10px 20px;
padding: 10px 20px 30px;
padding: 10px 20px 5px 30px;
```

### Atributo display

| Valor          | Descrição                                  |
| -------------- | ------------------------------------------ |
| `block`        | Ocupa toda a linha (`div`, `section`)      |
| `inline`       | Ocupa apenas o conteúdo (`span`, `a`)      |
| `inline-block` | Inline, mas permite definir `width/height` |
| `none`         | Esconde o elemento                         |
| `flex`         | Usa layout Flexbox                         |
| `grid`         | Usa layout CSS Grid                        |



### Unidades de medida

| Tipo          | Exemplo                                              | Descrição                            |
| ------------- | ---------------------------------------------------- | ------------------------------------ |
| **Absolutas** | `px`, `cm`, `mm`, `pt`                               | Fixas, não se ajustam à tela         |
| **Relativas** | `%`, `em`, `rem`, `vw`, `vh`                         | Dependem do elemento pai ou viewport |
| `em`          | Relativo ao tamanho da **fonte do elemento pai**     |                                      |
| `rem`         | Relativo à fonte do **elemento raiz (html)**         |                                      |
| `vw` / `vh`   | Relativo à largura/altura da **viewport** (1vw = 1%) |                                      |



### Cores

| Tipo            | Exemplo                     | Explicação                       |
| --------------- | --------------------------- | -------------------------------- |
| **Hexadecimal** | `#ff0000`                   | Vermelho puro (R=FF, G=00, B=00) |
| **RGB**         | `rgb(255, 0, 0)`            | Vermelho                         |
| **RGBA**        | `rgba(255, 0, 0, 0.5)`      | Vermelho com transparência       |
| **HSL**         | `hsl(0, 100%, 50%)`         | Matiz, saturação, luminosidade   |
| **HSLA**        | `hsla(120, 100%, 50%, 0.5)` | Com transparência                |


### Propriedades de texto

```css
p {
  color: red;
  background-color: yellow;
  font-style: italic;
  font-weight: bold;
  font-size: 20px;
  text-decoration: underline;
  text-transform: uppercase;
  text-align: center;
  line-height: 1.5;
  letter-spacing: 1px;
  word-spacing: 5px;
  text-indent: 40px;
  text-shadow: 2px 2px 5px gray;
}
```

### Tamanho e responsividade

| Propriedade              | Função                                                          |
| ------------------------ | --------------------------------------------------------------- |
| `width`, `height`        | Largura e altura                                                |
| `max-width`, `min-width` | Limites máximos e mínimos                                       |
| `auto`                   | Calculado automaticamente                                       |
| `overflow`               | Controla conteúdo que “transborda” (`hidden`, `scroll`, `auto`) |

 

### Position e Z-index

| Valor      | Descrição                                                |
| ---------- | -------------------------------------------------------- |
| `static`   | Padrão (fluxo normal)                                    |
| `relative` | Move em relação à posição original                       |
| `absolute` | Posiciona relativo ao **primeiro ancestral posicionado** |
| `fixed`    | Fixa na tela (mesmo com scroll)                          |
| `sticky`   | Fixa quando chega ao topo da tela                        |
| `z-index`  | Define a **ordem de sobreposição** (maior = na frente)   |



### Variáveis e herança

```css
/* define váriaveis globais */
:root {
  --primary-color: #0a1128;
}

body {
  color: var(--primary-color);
}
```
- `inherit` força a herança de um valor do pai.

```css
p {
color: inherit;
}
```


### Contadores no CSS

- Permitem numerar elementos automaticamente:

```css
body {
  counter-reset: secao;
}

h2::before {
  counter-increment: secao;
  content: "Seção " counter(secao) ": ";
}
```

### Media Queries

- Usadas para aplicar estilos dependendo do tamanho da tela.

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```
- tipos mais comuns:
    - `max-width`: até X pixels
    - `min-width`: a partir de X pixels
    - `orientation: landscape` (horizontal)
- https://developer.mozilla.org/pt-BR/docs/Web/CSS/Guides/Media_queries/Using

### Flexbox  

- Define um container flexível com `display: flex;`
- Controla o eixo principal (horizontal por padrão) e o eixo cruzado (vertical)

| Propriedade       | Função                        |
| ----------------- | ----------------------------- |
| `flex-direction`  | Direção (row, column)         |
| `justify-content` | Alinhamento no eixo principal |
| `align-items`     | Alinhamento no eixo cruzado   |
| `align-content`   | Alinha linhas extras          |
| `flex-wrap`       | Quebra ou não a linha         |
| `flex-grow`       | Quanto o item cresce          |
| `gap`             | Espaçamento entre itens       |

- https://css-tricks.com/snippets/css/a-guide-to-flexbox/



### Grid Layout

- Ativado com `display: grid;`
- Permite definir linhas e colunas com precisão.

```css
/* nesse caso, define 3 colunas */
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
}
```
- https://css-tricks.com/snippets/css/complete-guide-grid/






### AAAAAAA



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



- links que foram visitados e links que não foram visitados (a:link, a:visited)






- herança no css




- links de ancoras

- 
- flexbox (eixo principal, eixo perpendicular, align content, align items, justify content, cross start, cross axis, cross end, flex flow, flex grow)


- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://youtu.be/uHiSYokteNY?si=kGm4lEusCUBTHuff
- https://youtu.be/odYCJU6NHss?si=jl4YplC_dlWtTzuR
- criar variaveis no css - :root{--primary-color: #0a1128;}
- inherit é herança????
- criar contador no css???







