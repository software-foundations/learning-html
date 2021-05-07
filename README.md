# learning-html

HTML concepts

## Tags
- Generic Tag
- Properties:
1. id (selector => #): element identifier. Used to apply behavior generally
2. class (selector => .): used to apply style to same class elements
3. attribute (selector => [attr_name]): apply behavior (js) to personal one elms
4. style: inline style
```html
<tag></tag>
```
- Doctype: specify html5 doctype
```html
<!doctype html>
```

- Head: import things and set configurations (not visible)
```html
<head></head>
```

- Body: content which will be rendered (visible)
```html
<body></body>
```

- Headers: for more to less relavant
```html
<h1> ... <h6>
```

- Title: title of the page
```html
<head>
	<title>Some title</title>
</head>
```

- a: link to something
- Properties
1. href: url to redirect
```html
<a href="/">Some text</a>
```

- Header: the introduction
```html
<body>
	<header></header>
<body>
```

- Nav: Navigation bar
```html
<body>
	<nav>
		<a href="/">Some text</a>
	</nav>
<body>
```

- Footer: Footer of the page
```html
<body>
	...
	<footer></footer>
<body>
```

- Meta: encoding of the characters
- Properties:
1. charset: encoding
```html
<head>
	<meta charset="utf-8">
<head>
```

- Section: section of a page. Contains some content
```html
<body>
	<section></section>
</body>
```

- Aside: side content or menu. The position is defined by CSS
```html
<body>
	<aside></aside>
</body>
```

- Style: CSS code
```html
<head>
	<style></style>
</head>
```

- Span: non visual tag (like div)
```html
<body>
	<span></span>
</body>
```

- Br: line break
```html
<head>
	<br>
</head>
```

- Link: link a css/js file
- Properties
1. rel
```html
<head>
	<link rel="stylesheet" href="path_to_css_file">
</head>
```

## Tag Anatomy

- The HTML document is organized in tree of tags
- HMTL5 allows us to create our own tags with our own names to create components
- Tags can have params (0 or many)
- We can have our own tag params
- To defined tags have defined params (can/cannot be optional)
- Defined tags can have our own parameters
- Each defined tag has its atributtes
- Each tag has a purpose. It should be taken seariosly

There is tags ...

- with body
- without body
- autoclosed tags without body

## HTML page Anatomy
https://www.w3schools.com/html/html5_semantic_elements.asp

- head and body basically
- Semantic tags (aside, footer, header, section, article, etc) are preferable
- Non semantic tags (div, span, etc) should be avoided

- [file](coder/anatomiaHtml.html)
```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Anatomia HTML</title>
    </head>
    <body>
        <header>
            <h1>Exercícios HTML</h1>
        </header>
        <nav>
            <a href="/">Navegação 1</a>
        </nav>
        <section id="conteudo">
            Conteúdo
        </section>
        <aside>
            Lateral
        </aside>
        <footer>
            Rodapé
        </footer>
    </body>
</html>
```

## A bit of CSS

- Apply Style in elements
- Use selectors to select specifc elements

Selectors
1. tag (tag name)
2. id (#)
3. class (.)

Nested Selectors
- selector 1 > selector 2

Same style to more than one selectors
- selector 1, selector 2

[poucoDeCSS.html](coder/poucoDeCSS.html)
[poucoDeCSS.css](coder/poucoDeCSS.css)

## Estructuring the exercises

- Use Ajax request to render html content inside the page
- Do that by intercept the click event at the link in nav
- Use event.preventDefault() to avoid load new page by click on link in nav
- Use fetch(link.href).then(resp => resp.text()).then(html => { ... })
- This get the html content and we can use that to put it in a element

```javascript
document.querySelectorAll('[wm-nav]').forEach(link => {
            const conteudo = document.getElementById('conteudo')
            
            link.onclick = function(e) {
                e.preventDefault()
                fetch(link.getAttribute('wm-nav'))
                    .then(resp => resp.text())
                    .then(html => conteudo.innerHTML = html)
            }
        })
```

[index.html](coder/index.html)
[teste.html](coder/exercicios/teste.html)
[temp.html](coder/exercicios/temp.html)
- Install http-server
```sh
sudo npm i -g http-server
```

- Start http-server
```sh
cd coder/

http-server .
# or
http-sever -p <port> .
http-sever -p 9090 .
```
