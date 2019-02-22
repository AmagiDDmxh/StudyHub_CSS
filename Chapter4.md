### Chapter 4: Values and Units
#### Keywords, Strings, and Other Text Values
##### Global Keywords
- inherit.
    - Make an element's value of property as same as its parent as seen before
- initial
    - Sets the value of a property to the defined initial value
- unset
    - Acts as a universal stand-in for both **inherit** and **initial**
- all
    - For all property except **direction** and **unicode-bidi**

##### Strings
- String can be start and end with single or double quote ' "
- Newline can be made with escaping \ and then just type newline there or with Unicode reference \A where you want.

##### URLs
- Absolute URL **url(protocal://server/pathname)**
- Relative URL **url(pathname)**
    - In CSS the relative style sheets is relative to itself not to the HTML document
- Note there connot have space in between like **body {background: url (pathname);}**


##### Images
- Its syntax representation is *<image>*, which value is a *<url>* value. and *<image>* stand for one of the following:
    - *<url>* - A URL identifier, such as URL of an image
    - *<image-set>* - a set of images, **image-set()** could specify larger image be used for pc layouts or smaller for mobile design. Intended to approximate the behavior of **srcset** attribute for **picture** element.
    - *<gradient>* - gradient image, details in **Chapter 9.**

##### Identifiers
Few properties can accept an *identifier value*, when defining an *identifier*, take care that it wasn't *identical* to a valid keyword.


#### Numbers and Percentages
##### Integers
- value syntax: *<integer>*. e.g. **13, -42, 612**
- Invalid to set out of range
- But some property have *clamping*, it can set the value to the accepted closest to the value given.

##### Numbers
- value syntax: *<number>*. either an *<integer>* or real number. e.g. **2.7183, -3.1416, 6.2823**
- Same as *<integer>*, if it fall outside a defined range, considered invalid and would be ignore. 
- And *clamping*

##### Percentages
- value syntax: *<percentage>*. *<number>* follow a percentage sign **(%)**, such as **23% or 3.333%**


##### fractions
- The *fraction value* or *flex value* is a *<number>* followed by the label **fr**. Introduced by **Grid Layout**, **Chapter 13** talks more details

#### Distances
Used often as a unit to declare the length of value

##### Absolute Length Units
- *Inches* *(***in***)*
- *Centimeters* *(***cm***):* 2.54 centimeters = 1 inch
- *Millimeters* *(***mm***):* 10 millimeters = 1 centimeter
- *Quarter-millimeters (**q**):* 40 Q units = 1 centimeter. (Only Firefox supported **q** as of late 2016.)
- *Points (**pt**):* 72 points = 1 inch
- *Picas (**pc**)*: 1 pica = 12 points
- *Pixes (**px**):* CSS defined 96 pixes = 1 inch, but many user-agent ignore that..

##### Resolution Units
- *Dots per inch (**dpi**):* The number of display dots per linear inch.
- *Dots per centimeter (**dpcm**):* The number of display dots per centimeter.
- *Dots per pixel (**dppx**):* The number of display dots per pixel. As of CSS3, **1dppx** is equivalent to **96dpi**
- But that radio can change in future versions of CSS.

In late 2017, resolution units often used for media queries.
```css
@media (min-resolution: 500dpi) {
/* rules go here */
}
```

##### Relative Length Units
- **em and ex units**
    - **em** size is set to relatively equal to the **font-size** of the element
    - But when using as a value of **font-size**, it's relative to the font size their parent element
    - In theory, one em is equal to the width of a lowercase **m** in the font used
    - one ex is equal to the height of a lowercase **x** in the font being used.
- **The rem unit**
    - **Rem** size is set to have the same **font-size** value as the root element of the document
- **The ch nuit**
    - It is an intersting unit that its meant to be equal to *"one character"*
    - Follow by the CSS3 stand says, Equal to the advance measure of the "0" (ZERO, U+0030) glyph found in the font used to render it.
    - So it will calculate the width of the single font character including the built-in spacing around it.
        - Hits that **IE11** has had the mis-measured width of the calculations, it didn't include the space to either side of it. And its fixed in **Edge**
- **Viewport-relative units**
    - New addition to CSS3. Calculated with respect to the size of the viewport -- browser window, printable area, mobile device display, etc
    - Common viewport types are:
        - *Viewport width unit (**vw**):* Viewport width 937 pixels wide, **1vw = 9.37px**. changed alone with the browser window scale.
        - *Viewport length unit (**vh**):* Same above, but with viewport's height instead.
        - *Viewport minimux unit (**vmin**):* Is now base on the lesser one, either width or height.
        - *Viewport maximum unit (**vmax**):* Same as above but chose the greater one.
    - Mostly used with article that the heading scale alone with the viewport and in the mobile page.
    - ! late 2016, supported by all browser except Opera Mini, and **vmax** is not supported in Microsoft browsers.

#### Calculation values **
- Using **calc()** value, you can construct simple mathematical expressions.
- Follow with PMDAS(parentheses **( )**, multiplcation **\***, division **/**, addition **+**, substraction **-**) in precedence order.
- Permitted value types: *<length>, <frequency>, <angle>, <time>, <percentage>, <number>, <integer>*.
- **+** or **-**: In different unit type. like length unit combine with length unit `5em + 2px` is ok but not the number `5em + 2.7`.
- **\***: With at least one *<number>* type `5em * 2` not `5em * 2em`.
- **/**: The right side must be a *<number>* and not with 0.
- Whitespace is *required* to either side of **+** and **-** operators

#### Attribute Values
Are abandoned...

#### Colors
- Named color
- Rgb color and Rgba color
- Hexadecimal RGB colors and RGBa colors
- HSL and HSLa
- Keywords
    - **transparent**
    - **currentColor**

#### Angles
- **deg**
- **grad**
- **rad**
- **turn**

| Degrees | Gradians | Radians | Turns |
| --- | --- | --- | --- |
| 0deg | 0grad | 0rad | 0turn |
| 45deg | 50grad | 0.785rad | 0.125turn |
| 180deg | 200grad | 3.142rad | 0.5turn |
| 360deg | 400grad | 6.283rad | 1turn |

#### Time and Frequency
- The Time value syntax is *<time>* and is a *<number>* followed by either **s** (seconds) or **ms** (milliseconds).
- The frequency value syntax *<frequency>* is a *<number>* followed by either **Hz** (hertz) or **kHz** (kilohertz)

#### Position
```
[ [ left | center | right | top | bottom | <percentage> | <length> ]  | 
  [ left | center | right | <percentage> | <length> ]
  [ top | center | bottom | <percentage> | <length> ] |
  [ center | [ left | right ] [ <percentage> | <length> ]? ] &&
  [ center | [ top | bottom ] [ <percentage> | <length> ]? ] ] 
```

#### Custom Values
CSS variables (Custom properties)
````css
html {
    --base-color: #639;
    --highlight-color: #AEA;
}

h1 {color: var(--base-color);}
h2 {color: var(--highlight-color);}

/* Useful example */
html {    
    --gutter: 3ch;
    --offset: 1;
}
ul li {margin-left: calc(var(--gutter) * var(--offset));}
ul ul li {--offset: 2;}
ul ul ul li {--offset: 3;}
/*This particular example is basically the same as writing:*/
ul li {margin-left: 3ch;}
ul ul li {margin-left: 6ch;}
ul ul ul li {margin-left: 9ch;}

@supports (color: var(--custom)) {
    /* variable-dependent styles go here */
}
@supports (--custom: value) {
    /* alternate query pattern */
}
```