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


## Pesquisar mais
- seletores