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










## pesquisar mais
- containers x tags de bloco

- existem tags que são blocos. E existem tags que não podem ir dentro de outras???


- estado lógico x estado fisico

- tags small, s, u, sup, sub, q(citação)
- tags que não pode, vir dentro da tag p. porque não são tags inline: blockquote...???
- containers: span x div??
- tags nav, section, article, aside
- o que são elemetos que tem semantica???section??






## Containers x Tags de Bloco

**Containers** são **tags genéricas usadas apenas para agrupar conteúdo** — elas servem como “caixas” que não têm significado semântico próprio.

### Exemplos de containers:

* `<div>` → container **de bloco**
* `<span>` → container **inline**

Essas tags não dizem *o que o conteúdo é*, apenas o **organizam visualmente** ou **para aplicar CSS/JS**.

---

**Tags de bloco (block-level)** são aquelas que:

* Ocupam **toda a largura disponível**.
* Começam **sempre em uma nova linha**.
* Podem conter **outros elementos**, inclusive outros blocos ou inline.

Exemplos:

```html
<div>, <p>, <section>, <article>, <header>, <footer>, <nav>, <table>, <ul>, <ol>, <form>
```

### Diferença:

| Tipo          | Exemplo                         | Característica                            |
| ------------- | ------------------------------- | ----------------------------------------- |
| **Container** | `<div>`, `<span>`               | Agrupam elementos (sem significado)       |
| **Bloco**     | `<section>`, `<article>`, `<p>` | Estruturalmente ocupam um bloco na página |

---

## 🧩 “Existem tags que são blocos. E existem tags que não podem ir dentro de outras”

Sim!
Cada tag tem **regras de aninhamento** — ou seja, **onde ela pode ou não ser colocada**.

Por exemplo:

```html
<p>
  Isso é um parágrafo.
  <blockquote>Isso é uma citação longa.</blockquote> <!-- ERRADO -->
</p>
```

➡️ `<blockquote>` é uma **tag de bloco**, e o `<p>` só pode conter **elementos inline** (como `<a>`, `<span>`, `<strong>` etc).
Por isso, o código acima **é inválido** em HTML5.

✅ Forma correta:

```html
<p>Isso é um parágrafo.</p>
<blockquote>Isso é uma citação longa.</blockquote>
```

📘 **Regra geral:**

* Tags **de bloco** → podem conter *tags inline* e até outros blocos (dependendo da tag).
* Tags **inline** → só podem conter *outras inline* (não podem ter blocos dentro delas).

---



##  Tags `small`, `s`, `u`, `sup`, `sub`, `q`

| Tag       | Função                                                     | Exemplo                 | Visual           |
| --------- | ---------------------------------------------------------- | ----------------------- | ---------------- |
| `<small>` | Texto menor, usado para observações, direitos autorais etc | `<small>© 2025</small>` | Texto menor      |
| `<s>`     | Texto riscado (informação incorreta ou desatualizada)      | `<s>R$ 100</s>`         | ~~R$ 100~~       |
| `<u>`     | Sublinhado (sem semântica)                                 | `<u>Texto</u>`          | <u>Texto</u>     |
| `<sup>`   | Sobrescrito (em cima)                                      | x<sup>2</sup>           | x²               |
| `<sub>`   | Subscrito (em baixo)                                       | H<sub>2</sub>O          | H₂O              |
| `<q>`     | Citação curta, com aspas automáticas                       | `<q>Ser ou não ser</q>` | “Ser ou não ser” |

---

##  Tags que não podem ir dentro de `<p>`

O `<p>` (parágrafo) **só aceita conteúdo inline**.

Ou seja:

*  Pode conter: `<a>`, `<span>`, `<strong>`, `<em>`, `<img>`, `<small>` etc.
*  Não pode conter: `<div>`, `<section>`, `<blockquote>`, `<ul>`, `<table>`, `<form>`...

Motivo:
Essas são **tags de bloco**, e o parágrafo é pensado para conter **texto corrido**, não seções.

---

## Containers: `<span>` x `<div>`

| Tag      | Tipo       | Descrição                                                                           | Exemplo                                               |
| -------- | ---------- | ----------------------------------------------------------------------------------- | ----------------------------------------------------- |
| `<div>`  | **Bloco**  | Agrupa conteúdo em nível de bloco (ex: várias tags dentro de uma seção visual)      | `<div class="container"></div>`                       |
| `<span>` | **Inline** | Agrupa partes de texto dentro de uma linha, para aplicar estilo sem quebrar o fluxo | `O <span class="vermelho">texto</span> está colorido` |

 Resumo rápido:

* Use `<div>` para **agrupamentos grandes** (layout, seções).
* Use `<span>` para **pequenos trechos de texto** (estilização pontual).

---

##  Tags `nav`, `section`, `article`, `aside`

Essas são **tags semânticas estruturais**, introduzidas no HTML5.

| Tag         | Significado                          | Uso típico                        |
| ----------- | ------------------------------------ | --------------------------------- |
| `<nav>`     | Área de navegação                    | Menus, links principais           |
| `<section>` | Seção de conteúdo relacionada        | Blocos temáticos, capítulos       |
| `<article>` | Conteúdo independente e reutilizável | Post de blog, notícia, comentário |
| `<aside>`   | Conteúdo secundário ou lateral       | Barra lateral, anúncios, notas    |

### Exemplo:

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

---

##  O que são elementos com semântica?

Um **elemento semântico** é aquele que **tem um significado próprio**, tanto para humanos quanto para máquinas (navegadores, leitores de tela, buscadores).

Exemplo:

* `<section>` → indica uma **seção de conteúdo relacionada**.
* `<header>` → indica **cabeçalho** da página ou de uma seção.
* `<footer>` → indica **rodapé**.

Já `<div>` ou `<span>` **não têm semântica**, servem apenas para estruturar.

 Em resumo:

 **Semântica = significado.**
 Quando o HTML “fala o que é”, ele é semântico.

---








 
 












