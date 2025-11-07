## Curso HTML5

- tags são case insensitives
- existem tags com e sem corpo
- nas tags sem corpo, pode ou não ter uma barra no final:
```html
<meta>
<meta/>
```
- tag <head> define metadados sobre o html
- comentário em HTML:
```html
<!-- Exemplo de comentário -->
```
- estutrutura "obrigatória" de uma página HTML:
```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width">
    <title>Meu html</title>
</head>

<body>

</body>

</html>
```
- estilo de tag inline -> ```<span></span>```
- id são únicos, não pode ter mais de um id iguais na página
- class também são identificadores, mas diferente do id, elas podem se repetir
```html
    <h1 id="cabecalho-um" class="fundo-vermelho">
        texto texto
    </h1>
    <h1 id="cabecalho-dois" class="fundo-vermelho">
        texto texto texto
    </h1>
```
