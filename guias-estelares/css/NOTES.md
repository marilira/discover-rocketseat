## Content
- [CSS](#css)
- [Comentários](#comentários)
- [Anatomia](#anatomia-do-css)
- [Seletores](#seletores)
- [Box model](#box-model)
- [Origem do CSS](#origem-do-css)
- [Cascata](#a-cascata)
- [At-rules](#at-rules)
- [Shorthand](#shorthand)
- [Funções](#funções)
- [DevTools](#devtools)
- [Vendor Prefixes](#vendor-prefixes)

### CSS
O que CSS significa?

Cascading Style Sheet - Folha de estilo em cascata

A folha de estilos é um código para estilizar o HTML - HTML = estrutura/esqueleto - CSS = beleza/maquiagem. CSS não é uma linguagem de programação, é uma linguagem style sheet.

### Comentários
* Não irá afetar o seu código
* Ajuda a lembrar blocos de códigos
* Deixa dicas para leitura
* Ajuda outros a entender
* Serve para desabilitar partes do código
```css
/* Assim que se faz um comentário no css */
```

### Anatomia do CSS
```css
h1 {
    color: blue;
    font-size: 60px;
    background: gray;
}
```
* Seletor ( h1 )
* Declaração ( o que fica entre chaves )
* Propiedades ( color, font-size, background )
* Valor da propiedade ( blue, 60px, gray )
exe-2

### Seletores
O que são?

Os seletores servem para conectar um elemento HTML com o CSS.

#### Tipos de seletores
* Seletor Global `*` ( afeta todo o documento )
* Seletor de elemento `h1, h2, p, div`
* Seletor de ID `#box, #container`
* Seletor de classe `.red, .m-4`
* Attribute selector, Pseudo-class, Pseudo-element...
exe-3

### Box Model
O CSS trabalha com a ideia de caixas. O que são essas caixas? Assim como uma caixa de sapato, por exemplo.

Toda caixa tem seus limites ( altura, largura ), conteúdo dentro dela, espaços vazios por dentro, espaços entre elas.
* ( quase ) Tudo são caixas do CSS
* Posicionamentos, tamanhos, espaçamentos, bordas, cores
* Caixas podem ficar ao lado uma da outra, ou acima
* Elementos HTML são caixas
exe-4

### Origem do CSS
Como aplicar o CSS no meu HTML?

Formas de aplicar:
#### inline
```html
<h1 style="color: red">
    Título
</h1>
```

#### interno
```html
<head>
    <style>
          h1 {
              color: red;
          }
    </style>
</head>
```

#### externo
Deixar o CSS em um arquivo separado
```html
<link rel="stylesheet" href="style.css">
```

#### dentro do arquivo css
```css
@import 'https://fonts.googleapis.com/css2?family=Potta+One&display=swap';
```
ou 
```css
<style>
      @import url('https://fonts.googleapis.com/css2?family=Potta+One&display=swap');
</style>
```

### A Cascata
(Cascading) O que é?

A escolha do browser de qual regra aplicar caso haja muitas regras para o mesmo elemento.
* Seu estilo é lido de cima pra baixo.
É levado em consideração 3 fatores
1. Origem do estilo
2. Especificidade
3. Importância
exe-5

#### Origem do estilo
inline > tag style > tag link

#### Especificidade
É um cálculo matemático, onde, cada tipo de seletor e origem do estilo possuem valores a serem considerados.

0. Universal selector, combinators e negation pseudo-class (:not())
1. Element type selector e pseudo-elements (::before, ::after)
10. Classes e attribute selectors ([type="radio"])
100. ID selector
1000. Inline

#### Importância
```css
h1 {
    color: blue !important;
}
```
o important é o que possui mais peso/força. Em alguns casos é necessário utilizá-lo.

### At-rules
Regras com @
* Está relacionado ao comportamento do CSS
* Começa com o sinal `@` seguido de identificador e valor

Exemplos:
- @import /* incluir um CSS externo */
- @media /* regras condicionais para dispositivos */
- @font-face /* fontes externas */
- @keyframes /* animações */

```css
@import url("http://local.com/style.css");

@media (min-width: 500px) {
    /* rules here */
}

@font-face {
    /* rules here */
}

@keyframes nameofanimation {
    /* rules here */
}
```

### Shorthand
* junção de propriedades
* resumido
* legível

```css
{
  /* background properties */
  background-color: #000;
  background-image: url(images/bg.gif);
  background-repeat: no-repeat;
  background-position: left top;
  
  /* background shorthand */
  background: #000 url(images/bg.gif) no-repeat left top;
  
  /* font properties */
  font-size: italic;
  font-weight: bold;
  font-size: .8rem;
  line-height: 1.2;
  font-family: Arial, sans-serif;
  
  /* font shorthand */
  font: italic bold .8rem/1.2 Arial, sans-serif;
```

#### Detalhes
* não irá considerar propriedades anteriores
* valores não especificados irão assumir o valor padrão
* geralmente, a ordem descrita não importa, mas, se houver muitas propriedades com valores semelhantes poderemos encontrar problemas

#### Propriedades que aceitam shorthand
https://developer.mozilla.org/en-us/docs/Web/CSS/Shorthand_properties

### Funções
* nome seguido de abre e fecha parentesis
* recebe argumentos

```css
@import url("http://urlaqui.com/style.css");

{
  color: rgb(255, 0, 100);
  width: cal(100% - 10px);
}
```

### DevTools
Acesso por F12

### Vendor Prefixes
Permite que browsers adicione `features` a fim de colocar em uso alguma novidade que vemos no CSS. Exemplo:
```css
p {
    -webkit-background-clip: text;  /* Chrome, Safari, iOS e Android */
    -moz-background-clip: text;     /* Mozilla (Firefox) */
    -ms-background-clip: text;      /* Internet Explorer */
    -o-background-clip: text;       /* Opera */
}
```
http://ireade.github.io/which-vendor-prefix/

http://caniuse.com
