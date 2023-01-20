# relational-markup-lang
A markup language that takes inspiration from HTML, but removed from HTML's tree structure using prepositions.

## Example
```rml
body { header, .par1, footer }
header in body { Untitled Document }
#par1 (tag: main, class: inverted) after header { Lorem ipsum dolor sit amet... }
aside for #par1 {
  Lorem ipsum is a filler phrase used commonly among developers.
}
footer after article { Copyright information }
```

## Example translated to HTML
```html
<body>
  <header>
    Untitled Document
  </header>
  <main id="par1" class="inverted">
    Lorem ipsum dolor sit amet...
    <aside>
      Lorem ipsum is a filler phrase used commonly among developers.
    </aside>
  </main>
  <footer>
    Copyright information
  </footer>
</body>
```

## Example explanation
Our example shows nested tags. Within body is a header, main, and footer (main has been given the name `.par1` by the programmer). Later, the example defines what relations each of those tags has to each other—the header is in the body, par1 is after the header, and the footer is after par1. A stylesheet could define these prepositions, for example making `after` display the target content below the referred content with 50px padding, or it could display the target content 50 seconds afterward. The relation `for` could be used for asides as in this example, or captions for images, or labels for radio button sets, or legends for graphs, for a few examples.

## Tags, IDs and relations
Tags are used to apply default presentation to content. A tag is not necessary, but if a tag isn't used, then a class must be.
IDs (the nouns prefixed by `#`) have no inherent meaning, but can be used to make intent more clear, or to style specific content differently.
Relations have no inherent meaning besides their default presentation. A user can define whatever words they want as relations, to have whatever presentation they want. The only syntactic restriction on relations is that they contain no whitespace. Relations are optional, but if used must be followed by the name of a tag or an ID.

## Classes
Precisely the same idea as HTML.

## Scope
Curly brackets define scope. To improve the legibility of the example, one might instead write
```rml
body { header, par1, footer } {
  header in body { Untitled Document }
  par1 (main) after header { Lorem ipsum dolor sit amet... }
  aside for .par1 {
    Lorem ipsum is a filler phrase used commonly among developers.
  }
  footer after article { Copyright information }
}
```
which has no effect on the rendering of the document, but shows the tree structure of this particular example.
