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
- seletores (.,*, #)
- box model, box-sizing: border-box;
- display: block;