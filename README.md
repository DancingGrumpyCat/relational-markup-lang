# relational-markup-lang
A markup language that takes inspiration from HTML, but removed from HTML's tree structure using prepositions.

## Example
```rml
body { header, par1, footer }
header in body { Untitled Document }
par1 (main) after header { Lorem ipsum dolor sit amet... }
footer after article { Copyright information }
```

## Example translated to HTML
```html
<body>
  <header>
    Untitled Document
  </header>
  <main>
    Lorem ipsum dolor sit amet...
  </main>
  <footer>
    Copyright information
  </footer>
</body>
```

## Example explanation
Our example shows nested tags. Within body is a header, main, and footer (main has been given the name "par1" by the programmer). Later, the example defines what relations each of those tags has to each other—the header is in the body, par1 is after the header, and the footer is after par1. A stylesheet could define these prepositions, for example making `after` display the target content below the referred content with 50px padding, or it could display the target content 50 seconds afterward.

## Scope
Curly brackets define scope. To improve the legibility of the example, one might instead write
```rml
body { header, par1, footer } {
  header in body { Untitled Document }
  par1 (main) after header { Lorem ipsum dolor sit amet... }
  footer after article { Copyright information }
}
```
which has no effect on the rendering of the document, but shows the tree structure of this particular example.
