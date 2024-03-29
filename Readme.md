![Project Demo](https://github.com/cipriancozma/css-foundations/assets/38767799/897def56-7c31-4e63-b144-e68f6df510cf)


## How CSS is rendered

---

- Browser loads HTML
- Converts HTML to the DOM
- Fetches linked resources
- Browser parses CSS
- Render tree is laid out
- UI is painted

## Specificity

---

1. Inheritance

- occurs when an inheritable CSS property (i.e. color) is not set directly on an element, the parent chain is traversed until a value for that property is found.

2. Specificity

- the algorithm used by browsers to determine which CSS declaration should be applied. Each selector has a calculated weight. The most specific weight wins.

ID Selector: 1 - 0 - 0

Class Selector: 0 - 1 - 0

Type Selector: 0 - 0 - 1

`.body .text p {
    ...
}`

| ID  | Class | Type |
| :-: | :---: | :--: |
|     |   2   |  1   |

Inline Styles - have higher specificity than IDs

!important - override all the styles (not recommended)

### Colors

---

- Named Color

`color: red;`

- Hexadecimal

`color: #0000FF;`

- RGB

`color: rgb(31, 120, 50)`

- RGBA

`color: rgba(255, 255, 255, .5)`

- HSL

`color: hsl(50 80% 40%)`

### Fonts & Typography

---

**Font families** specifies a list of one or more font family names.

`font-family: Georgia, serif;`

Related to the typography:

1. :+1: If we are using `**em**` for font-size -> relative to the parent's font-size

`html {
font-size: 16px;
}

div {
font-size: 2em;
}

p {
font-size: 2em;
}`

For **p** font-size will be equal to:

16px \* 2em = 32px

32px \* 2em = 64px

2. :+1: If we are using `**rem**` for font-size -> relative to the root font-size

`html {
font-size: 16px;
}

div {
font-size: 2rem;
}

p {
font-size: 2rem;
}`

For **p** font-size will be equal to:

16px \* 2rem = 32px

16px \* 2rem = 32px

3. :+1: If we are using `**%**` for font-size:

` html {
font-size: 16px;
}

div {
font-size: 120%;
}

p {
font-size: 120%;
} `

For **%** font-size will be equal to:

120% => 1.2 \* 16 = 19.2px

120% => 1.2 \* 19.2 = 23.04px

### Combinators

---

##### Descendent Selector

`

<ul>
<li><a href="#">Link 1</a></li>
<li><a href="#">Link 2</a></li>
<li><a href="#">Link 3</a></li>
</ul>
`

`ul li a {
    color: red
}`

##### Child Combinators (Direct Descendants)

`

<div class="text">
    <p>Here is some text. </p>
    <div>
        <p>Here is some more text. </p>
    </div>
</div>
`

`div.text > p {
    font-weight: bold;
}`

##### Adjacent Sibling Combinators

`

<h1>Hello world!</h1>
<p>This is a paragraph!</p>
<p>This is another paragraph</p>
`

`h1 + p {
    color: red
}`

The first paragraph after the **h1** will be with red color

##### General Sibling Combinators

`

<p>This is a paragraph </p>
<code> Here is some code </code>
<code> Here is some more code </code>
<p>This is another paragrah</p>
<div>
    <code>Here is the last block of code</code>
</div>
`

`p ~ code {
    color: red
}`

The first and second **code** element will be in red.

### Block Element Modifier (BEM)

---

BEM is a design methodology that helps create reusable components and code sharing.

**Other Methodologies**:

- OOCSS
- SMACSS
- SUITCVSS
- Atomic
- BEM

BEM in practice

`.block__element--modifier`

For instance:

`.form
.form__input
.form__input--disabled
.form__input--large`

### BOX Model

---

From inner to outer: Content -> Padding -> Border -> Margin

### Pseudo Classes, Elements & Transitions

---

###### Input Pseudo-Classes:

- :enabled
- :disabled
- :checked
- :required
- :optional

###### Resource State Pseudo-Classes:

- :playing
- :paused

###### Tree Structural Pseudo Classes:

- :root
- :empty
- :nth-child
- :nth-last-child
- :first-child
- :last-child
- :nth-of-type

###### User Action Pseudo Classes:

- :hover
- :active
- :focus

###### Functional Pseudo Classes:

- :is()
- :not()

###### Pseudo-Elements:

- ::before
- ::after
- ::placeholder
- ::first-line
