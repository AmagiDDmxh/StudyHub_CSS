#### Chapter 3: Specificity and The Cascade

##### Specificity
- Specificity **determines, which CSS rule is applied** by the browsers
- Specificity can be expressed in four parts, like **0,0,0,0**
- **ID selector** add **0,1,0,0**
- **Class, pseudo-class** and **Attribute Selectors** add **0,0,1,0**
- **Element selectors** and **Pseudo Element Selecotrs** add **0,0,0,1**
- **Inline Style** Specificity gives **1,0,0,0**
- **Specificity value like** **0,0,1,0** is superior than **0,0,0,23**
- **Specificity value** **0,0,0,0** is superior than having no specificity
- **universal selector like \*** have **0,0,0,0** specificity
- when **!important** is marked then they don't share the same comparison with non-important group

Basic Specificity Example
```css
h1 {color: red;}                                  /* specificity = 0,0,0,1 */
p em {color: purple;}                        /* specificity = 0,0,0,2 */
.grape {color: purple;}                      /* specificity = 0,0,1,0 */ 
*.bright {color: yellow;}                    /* specificity = 0,0,1,0 */ 
p.bright em.dark {color: maroon;}  /* specificity = 0,0,2,2 */
#id216 {color: blue;}                        /* specificity = 0,1,0,0 */
div#sidebar *[href] {color: silver;}   /* specificity = 0,1,1,1 */
```
##### Inheritance
- Some basic element style property are initially inherite by default, hence one element styled color attribute can propagate to its descendant elements
- But inherited property have no specificity at all. The common case was that when writing hyperlink inside a element, but the element styled property is not applied to the hyperlink since a hyperlink in a browser have **a:link { color: blue; }** by default


##### Cascade
- Cascading Rules
    1. Find all rules that contain a selector that matches a given element. 
    2. Sort all declarations applying to the given element by explicit weight. Those rules marked !important have a higher weight than those that are not.
    3. Sort all declarations applying to the given element by origin. There are three basic origins: author, reader, and user agent. Under normal circumstances, the author’s styles win out over the reader’s styles. !important reader styles are stronger than any other styles, including !important author styles. Both author and reader styles override the user agent’s default styles. 
    4. Sort all declarations applying to the given element by specificity. Those elements with a higher specificity have more weight than those with lower specificity. 
    5. Sort all declarations applying to the given element by order. The later a declaration appears in the style sheet or document, the more weight it is given. Declarations that appear in an imported style sheet are considered to come before all declarations within the style sheet that imports them.