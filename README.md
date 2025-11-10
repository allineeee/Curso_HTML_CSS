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
- html semantico: por exemplo usar as tags ```<h>``` ajuda quando um leitor para deficientes visuais usar o site
- existem tags que são blocos. E existem tags que não podem ir dentro de outras
- toda tag html pode receber um atributo style, que recebe um css dentro
- tag ```<b>``` e tag ```<strong>``` deixam um texto em negrito. Porém, a tag ```<strong>``` é uma tag semântica, ela deixa a palavra "mais forte" para o leitor.
- tags semânticas
- bold x strong
- estado lógico x estado fisico
- tag i x em (ambas deixam o texto em itálico)
- tag de link ```<a href="" target="_blank">coloca link</a>```. O target define configurações para seu link, o '_blank', por exemplo, abre o link em uma nova aba.
- tags small, s, u, sup, sub, q(citação)
- tags inlines
- tags que não pode, vir dentro da tag p. porque não são tags inline: blockquote...
- containers: span x div
- tags nav, section, article, aside
- elemetos que tem semantica???section??
- padding: Top Direita Bottom Esquerda (sentido horário)
- li x ul x ol(ver types e start) x dl
- tabelas tr x th, colspan, rowspan
- é proibido aninhar um form dentro de outro form??



