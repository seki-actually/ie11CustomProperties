# CSS Variables for IE11
Custom Properties polyfill for IE11


## It can:
- handle dynamic added `<style>`, `<link>`-elements
- handle dynamic added html-content
- cascade works
- inheritance works
- chaining `--bar:var(--foo)`
- fallback `var(--color, blue)`
- :focus, :target, :hover
- js-integration:  
    - `style.setProperty('--x','y')`
    - `style.getPropertyValue('--x')`
    - `getComputedStyle(el).getPropertyValue('--inherited')` !!
- under 2k gziped, who would have thought that?

## Demo:
https://rawcdn.githack.com/nuxodin/ie11CustomProperties/2ba50775d45dcf80bd071c31e136bcbc2dc720bc/test.html

## Limitations
### styles in element-attributes
There is no way to get the raw content of style-attributes in IE11
I could implement one of these variants: 
- `<div style="--color:blue" ie-style="--color:blue">` advantage: faster because I can query for `[ie-style]`  
- `<div style="--color:blue; -ie-color:blue">` advantage: less code  
### specificity for properties containing "var()"
...is always little highter, cause each selector gets an additional class-selector  
eg. `#header` results in `#header.iecp_u44`


## Help wanted!
Please test and report bugs.  
And add a ⭐️ and tweet about if you like it.
