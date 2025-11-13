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
- `lang="pt-BR"` -> define o idioma da página (importante para acessibilidade)
- `meta viewport` -> garante responsividade em dispositivos móveis
- `alt` nas imagens -> texto alternativo para descrever algo (importante para a acessibilidade da página)


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
    - Podem conter outros elementos dentro delas, inclusive outros blocos ou inline.
- Inline: não quebram linha e ocupam apenas o espaço do conteúdo - ```<span>```, ```<a>```, ```<strong>```
- Containers: elementos usados para agrupar e estruturar elementos em uma página: 
    - ```<div>``` -> bloco genérico (sem significado semântico)
    - ```<span>``` -> container inline genérico
- Tags de bloco -> podem conter tags inline e até outros blocos (dependendo da tag).
- Tags inline -> só podem conter outras inline (não podem ter blocos dentro delas).
- a tag `<p>`, por exemplo, só aceita conteúdo inline dentro dela.

### HTML Semântico

- Usar tags semânticas melhora acessibilidade (por exemplo, softwares para deficientes visuais) e SEO.
- tags semânticas possuem um significado próprio, tanto para humanos quanto para leitores de telas etc...
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
| Não ordenada | `<ul>` | Itens com marcadores (bolinha)                          |
| Ordenada    | `<ol>` | Itens numerados (`type="A"`, `type="I"`, etc)  |
| Definição    | `<dl>` | Lista de termos e definições (`<dt>` e `<dd>`) |

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

##  Formulários

- Um `<form>` não pode conter outro `<form>` dentro dele
- `<label>` associada a um campo é clicável quando o `for` corresponde ao `id` do input.
- Exemplo:
  ```html
  <label for="nome">Nome:</label>
  <input id="nome" type="text">
  ```
- `accept="image/*"` -> limita o tipo de arquivo aceito (nesse caso, imagens)
- `cols` e `rows` no `<textarea>` definem o tamanho da área de texto (o cols pode contar o número de caracteres).
  ```html
  <textarea rows="5" cols="30"></textarea>
  ```
- tipos mais comuns de inputs: text, number, email, password, checkbox, radio, date, file, color, range, submit 


##  CSS Inline

- Toda tag pode receber o atributo `style`:
```html
  <p style="color: red; font-size: 20px;">Texto colorido</p>
```

## Containers x Tags de Bloco

- Containers são tags genéricas usadas apenas para agrupar conteúdo — elas servem como “caixas” que não têm significado semântico próprio.
- Exemplos: 
    - `<div>` -> container de bloco
    - `<span>` -> container inline
- Essas tags apenas organizam visualmente o conteúdo para aplicar CSS/JS
- tags de bloco -> estruturalmente ocupam um bloco na página
- `<div>` -> é uma tag de bloco, agrupa várias tags dentro de uma seção visual
```html
<div class="container"></div>
```
- `<span>` -> é uma tag inline, agrupa partes de um texto dentro de uma linha
```html
<p>O <span class="vermelho">texto</span> está colorido</p>
```













##  Tags `nav`, `section`, `article`, `aside`

- tags semânticas estruturais, do HTML5.

| Tag         | Significado                          | Quando usar                        |
| ----------- | ------------------------------------ | --------------------------------- |
| `<nav>`     | Área de navegação                    | Menus, links principais           |
| `<section>` | Seção de conteúdo relacionada        | Blocos temáticos, capítulos       |
| `<article>` | Conteúdo independente e reutilizável | Post de blog, notícia, comentário |
| `<aside>`   | Conteúdo secundário ou lateral       | Barra lateral, anúncios, notas    |

```html
<main>
  <article>
    <h2>Notícia</h2>
    <p>Texto do artigo...</p>
  </article>

  <aside>
    <h3>Outras notícias</h3>
  </aside>
</main>
```
