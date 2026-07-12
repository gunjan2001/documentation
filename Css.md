# CSS:

The cascade algorithm is split into 4 distinct stages.
**Position and order of appearance**: the order of which your CSS rules appear
**Specificity:** an algorithm which determines which CSS selector has the strongest match
**Origin**: the order of when CSS appears and where it comes from, whether that is a browser style, CSS from a browser extension, or your authored CSS
**Importance**: some CSS rules are weighted more heavily than others, especially with the !important rule type

## specificity:

**Universal selector**

- A universal selector (\*) has no specificity and gets 0 points.
- An element (type) or pseudo-element selector gets 1 point of specificity .

**Class, pseudo-class, or attribute selector #**

- A class, pseudo-class or attribute selector gets 10 points of specificity.

**ID selector #**

- An ID selector gets 100 points of specificity, as long as you use an ID selector (#myID) and not an attribute selector ([id="myID"]).

**Inline style attribute #**

- CSS applied directly to the style attribute of the HTML element, gets a specificity score of 1,000 points.

**!important rule #**

- Lastly, an !important at the end of a CSS value gets a specificity score of 10,000 points.

## CSS Margins:

- The CSS `margin` properties are used to create space around elements, outside of any defined borders.
- `margin` will be `possible` in `minus` value.

### margin : `auto`:

- horizontally center the element within its container.

## CSS padding:

- Padding is used to create space around an element's content, inside of any defined borders.
- length - specifies a padding in px, pt, cm, etc.
- `%` : specifies a padding in % of the width of the containing element
- `inherit` : specifies that the padding should be inherited from the parent element
- Note: Negative values are not allowed.

## CSS Height, Width and Max-width:

- The CSS height and width properties are used to set the `height` and `width` of an `element`.
- The CSS `max-width` property is used to set the maximum width of an element.

### height and width Values:

- auto - This is default. The browser calculates the height and width
- length - Defines the height/width in px, cm, etc.
- % - Defines the height/width in percent of the containing block
- initial - Sets the height/width to its default value
- inherit - The height/width will be inherited from its parent value

## Box Model:

- Content - The content of the box, where text and images appear
- Padding - Clears an area around the content. The padding is transparent
- Border - A border that goes around the padding and content
- Margin - Clears an area outside the border. The margin is transparent

## Border Box:

- In the border box model, the width and height of an element include its content, padding, and border. This means that the specified width and height values include the space taken up by the content, padding, and border combined.

- Width = content width + padding + border
- Height = content height + padding + border

## Content Box:

- In the content box model, the width and height of an element are calculated excluding padding, border, and margin.
- In other words, the content box represents the innermost dimensions of an element that holds its actual content.

- Width = content width
- Height = content height

### Text Decoration:

- All links in HTML are underlined by default. Sometimes you see that links are styled with no underline. The `text-decoration: none;` is used to remove the underline from links, like this.

## css display:

- display: `inline` -> it will take the space as it's size is there.
- `block` -> we can set width of block element.
- `inline-block` :means in one line it will apear and we can set height and width of it.

## CSS Position:

- properties:

- **static**: Default value. Here the element is positioned according to the normal flow of the document.
- **absolute**: Here the element is positioned relative to its parent element. The final position is determined by the values of left, right, top, bottom.
- **fixed**: This is similar to absolute except here the elements are positioned relative to the <html> element.
- **relative**: Here the element is positioned according to the normal flow of the document and positioned relative to its original/ normal position.
- **initial**: This resets the property to its default value.
- **inherit**: Here the element inherits or takes the property of its parent.

## fixed vs sticky:

- **the 'fixed' position sets the position of the HTML elements according to the viewport, and**
- **the 'sticky' position sets the position according to the parent element**
- fixed: It always overrides the other elements.
- sticky: It overrides the other elements when the element reaches the offset and becomes fixed.

## CSS Combinators:

- descendant selector (space)
- child selector (>)
- adjacent sibling selector (+)
- general sibling selector (~)

### Descendant Selector:

- The following example selects all `<p>` elements inside `<div>` elements: </br>
  ![img](/images/decendentselector.png)

### Child Selector (>):

- The child selector selects all elements that are the children of a specified element.</br>
  ![img](/images/child.png)

### Adjacent Sibling Selector (+):

- "adjacent" means "immediately following".
- The following example selects the first `<p>` element that are placed immediately after `<div>` elements.

### General Sibling Selector (~):

- selects all elements that are next siblings of a specified element.

## What are Pseudo-classes?

- A pseudo-class is used to define a special state of an element.

### Hover on `<div>`:

- `:hover` pseudo-class
- `:visited`, `:target`, `:active`, `:focus` etc.
- `:first/last-child` Pseudo-class :- pseudo-class matches a specified element that is the first child of another element.

## What are Pseudo-Elements?

- A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s).
- ::after, ::before, ::first-letter, ::first-line
- For example, it can be used to:
  - Style the first letter, or line, of an element
  - Insert content **before**, or **after**, the content of an element

## Units:

```
cm: centimeters
mm: millimeters
in: inches (1in = 96px = 2.54cm)
pixels (1px = 1/96th of 1in)
pt: points (1pt = 1/72 of 1in)
pc: picas (1pc = 12 pt)
```

**relative**

```
em: Relative to the font-size of the element (2em means 2 times the size of the current font)

ex : Relative to the x-height of the current font (rarely used)

ch : Relative to width of the "O" (zero)

rem : Relative to font-size of the root element

vw: Relative to 1% of the width of the viewport

vh: Relative to 1% of the height of the viewport*

```

## What is !important?

- The !important rule in CSS is used to add more importance to a property/value than normal.

## CSS Variables:

- The var() function is used to insert the value of a CSS variable.
- The syntax of the var() function is as follows:
  `var(--name, value)` </br>

## Media quries:

- Syntax: </br>
  `@media not|only mediatype and (expressions) {
  CSS-Code;
}`

- **all**: Used for all media type devices
- **print**: Used for printers
- **screen**: Used for computer screens, tablets, smart-phones etc.
- **speech**: Used for screenreaders that "reads" the page out loud

## Z Index:

- The z-index property specifies the stack order of an element.
- An element with greater stack order is always in front of an element with a lower stack order.
