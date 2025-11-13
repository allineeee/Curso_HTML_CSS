## Curso HTML5

### Teoria

- As tags HTML são case-insensitive (não diferenciam maiúsculas e minúsculas), mas por convenção usam minúsculas
- Existem tags com corpo (que possuem abertura e fechamento) e tags sem corpo (pode ou não ter uma barra no final):
```html
    <p>Com corpo</p>
    <meta /> <!-- Sem corpo -->
```
- A tag ```<head>``` define metadados do documento (charset, título, links de estilo, scripts etc).
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
    <!-- CSS também pode ir aqui. Usando arquivo ou a tag style -->
</head>
<body>
    <!-- Conteúdo visível -->
</body>
</html>
```

### IDs e Classes

- Id são únicos, não devem se repetir na página
- Classes também são identificadores, mas diferente do id, podem se repetir e uma tag pode ter várias classes
```html
    <h1 id="cabecalho-um" class="fundo-vermelho outra-classe">
        texto texto
    </h1>
    <h1 id="cabecalho-dois" class="fundo-vermelho">
        texto texto texto
    </h1>
```


### Tipos de tags

- Existem tags que são blocos, inline e containers
- Blocos (Block-level): ocupam toda a largura disponível e começam em nova linha - ```<div>```, ```<p>```, ```<section>```
- Inline: não quebram linha e ocupam apenas o espaço do conteúdo - ```<span>```, ```<a>```, ```<strong>```
- Containers: elementos usados para agrupar e estruturar elementos em uma página: 
    - ```<div>``` -> bloco genérico (sem significado semântico)
    - ```<span>``` -> container inline genérico

### HTML Semântico

- Usar tags semânticas melhora acessibilidade (por exemplo, softwares para deficientes visuais) e SEO.
- ```<strong>``` indica importância, enquanto ```<b>``` apenas muda o estilo visual.
- ```<em>``` tem valor semântico (ênfase), enquanto ```<i>``` apenas aplica itálico.
- principais tags semânticas: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`  

### Links

```html
<a href="https://site.com" target="_blank">Abrir em nova aba</a>
```
- `href`: destino do link
- `target="_blank"`: abre o link em nova aba (mas o target também pode ter outras configurações)
- Também pode ter `title` (texto ao passar o mouse)

###  Listas

| Tipo             | Tag    | Descrição                                      |
| ---------------- | ------ | ---------------------------------------------- |
| **Não ordenada** | `<ul>` | Itens com marcadores (bolinha)                          |
| **Ordenada**     | `<ol>` | Itens numerados (`type="A"`, `type="I"`, etc)  |
| **Definição**    | `<dl>` | Lista de termos e definições (`<dt>` e `<dd>`) |

- Exemplo de lista ordenada, que começa em 'C':

```html
<ol type="A" start="3">
  <li>Item</li>
</ol>
```

### Tabelas

- `<th>` -> cabeçalho da coluna
- `<td>` -> célula
- `colspan` e `rowspan` mesclam células
- `<caption>` usado para adicionar título na tabela

```html
<table>
  <tr>
    <th>Nome</th>
    <th>Idade</th>
  </tr>
  <tr>
    <td>Alline</td>
    <td>29</td>
  </tr>
</table>
```





### AAAA







## pesquisar mais
- containers e tags bloco

- existem tags que são blocos. E existem tags que não podem ir dentro de outras
- toda tag html pode receber um atributo style, que recebe um css dentro



- estado lógico x estado fisico

- tags small, s, u, sup, sub, q(citação)
- tags que não pode, vir dentro da tag p. porque não são tags inline: blockquote...
- containers: span x div
- tags nav, section, article, aside
- elemetos que tem semantica???section??
- padding: Top Direita Bottom Esquerda (sentido horário)

- é proibido aninhar um form dentro de outro form??
- label são clicáveis?
- accept="image/*"???
- tipos da tag input
- cols e rows no textareas, cols são a quantidade de caracteres????




 
 





##  Formulários

* Um `<form>` **não pode conter outro `<form>`** (não é permitido aninhar).
* `<label>` associada a um campo é **clicável** quando o `for` corresponde ao `id` do input.

  ```html
  <label for="nome">Nome:</label>
  <input id="nome" type="text">
  ```
* `accept="image/*"` → limita o tipo de arquivo aceito (nesse caso, imagens)
* `cols` e `rows` no `<textarea>` definem o **tamanho da área de texto**, não o número de caracteres exatos.

  ```html
  <textarea rows="5" cols="30"></textarea>
  ```

### Tipos comuns de `<input>`

| Tipo     | Descrição                |
| -------- | ------------------------ |
| text     | texto livre              |
| number   | números                  |
| email    | valida formato de e-mail |
| password | campo de senha           |
| checkbox | múltipla escolha         |
| radio    | escolha única            |
| date     | data                     |
| file     | upload de arquivo        |
| color    | seletor de cor           |
| range    | controle deslizante      |
| submit   | botão de envio           |

---

##  CSS Inline

* Toda tag pode receber o atributo `style`:

  ```html
  <p style="color: red; font-size: 20px;">Texto colorido</p>
  ```

---

##  Box Model e espaçamento

* `padding`: espaçamento **interno** (dentro da borda)
* `margin`: espaçamento **externo**
* Ordem dos valores: **Top → Right → Bottom → Left** (sentido horário)

---

##  Extras úteis

* `lang="pt-BR"` → define o idioma da página (importante para acessibilidade)
* `meta viewport` → garante responsividade em dispositivos móveis
* `alt` nas imagens → texto alternativo (importante para SEO e acessibilidade)

---


