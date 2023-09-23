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
