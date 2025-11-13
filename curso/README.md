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



- id são únicos, não pode ter mais de um id iguais na página
- class também são identificadores, mas diferente do id, elas podem se repetir, e é possivel ter mais de uma classe dentro de uma tag
```html
    <h1 id="cabecalho-um" class="fundo-vermelho outra-classe">
        texto texto
    </h1>
    <h1 id="cabecalho-dois" class="fundo-vermelho">
        texto texto texto
    </h1>
```
- html semântico: usar as tags ```<h>```, por exemplo, ajuda quando um leitor para deficientes visuais lê o site
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
- label são clicáveis?
- accept="image/*"???
- tipos da tag input
- cols e rows no textareas, cols são a quantidade de caracteres????





## pesquisar mais
- estilo de tag  e block elementos -> ```<span></span>```

##  Identificadores e Classes

* **id** é único — não deve se repetir na página.
* **class** pode se repetir e uma tag pode ter várias classes:

  ```html
  <h1 id="cabecalho-um" class="fundo-vermelho outra-classe">Texto</h1>
  <h1 id="cabecalho-dois" class="fundo-vermelho">Outro texto</h1>
  ```

---

##  Tipos de tags

| Tipo            | Exemplo                     | Características                                          |
| --------------- | --------------------------- | -------------------------------------------------------- |
| **Block-level** | `<div>`, `<p>`, `<section>` | Ocupam toda a largura disponível e começam em nova linha |
| **Inline**      | `<span>`, `<a>`, `<strong>` | Não quebram linha; ocupam apenas o espaço do conteúdo    |

### Containers

* `<div>` → bloco genérico (sem significado semântico)
* `<span>` → container **inline** genérico

---

##  HTML semântico

* Usar tags semânticas melhora **acessibilidade e SEO**.
* Exemplo: `<strong>` indica importância, enquanto `<b>` apenas muda o estilo visual.
* Exemplo: `<em>` tem valor semântico (ênfase), enquanto `<i>` apenas aplica itálico.

### Principais tags semânticas

| Tag         | Função                                   |
| ----------- | ---------------------------------------- |
| `<header>`  | Cabeçalho da página ou seção             |
| `<nav>`     | Navegação principal                      |
| `<main>`    | Conteúdo principal                       |
| `<section>` | Agrupa conteúdo relacionado              |
| `<article>` | Conteúdo independente (ex: post de blog) |
| `<aside>`   | Conteúdo complementar ou barra lateral   |
| `<footer>`  | Rodapé da página                         |

---

##  Texto e formatação

* `<strong>` → negrito semântico
* `<b>` → apenas visual
* `<em>` → itálico semântico
* `<i>` → apenas visual
* `<u>` → sublinhado
* `<s>` → texto riscado
* `<small>` → texto menor
* `<sup>` → sobrescrito
* `<sub>` → subscrito
* `<q>` → citação curta (usa aspas automáticas)
* `<blockquote>` → citação longa (bloco)
* **Evite usar `<b>` e `<i>` apenas para aparência** — prefira CSS.

---

##  Links

```html
<a href="https://site.com" target="_blank">Abrir em nova aba</a>
```

* `href`: destino do link
* `target="_blank"`: abre o link em nova aba
* Também pode ter `title` (texto ao passar o mouse)

---

##  Listas

| Tipo             | Tag    | Descrição                                      |
| ---------------- | ------ | ---------------------------------------------- |
| **Não ordenada** | `<ul>` | Itens com marcadores                           |
| **Ordenada**     | `<ol>` | Itens numerados (`type="A"`, `type="I"`, etc)  |
| **Definição**    | `<dl>` | Lista de termos e definições (`<dt>` e `<dd>`) |

Exemplo:

```html
<ol type="A" start="3">
  <li>Item</li>
</ol>
```

---

##  Tabelas

```html
<table>
  <tr>
    <th>Nome</th>
    <th>Idade</th>
  </tr>
  <tr>
    <td>Alline</td>
    <td>25</td>
  </tr>
</table>
```

* `<th>` = cabeçalho da coluna
* `<td>` = célula
* `colspan` e `rowspan` mesclam células
* Use `<caption>` para título da tabela

---

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


