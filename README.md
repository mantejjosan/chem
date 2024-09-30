# How to render Chemical and Mathematical Equations + Mermaid Diagrams

## Prerequisites
1. Have an HTML file.

## Steps

> 1. To include MathJax CDN for rendering chemical and mathematical equations copy the following script tag and paste inside the head(or body) tag.
> ```
> <script type="text/javascript" async
>       src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"
>       id="MathJax-script"
>       data-mathjax-config='{
>         "loader": {
>           "load": ["[tex]/mhchem"]
>         },
>         "tex": {
>           "inlineMath": [["$", "$"], ["\\(", "\\)"]],
>           "displayMath": [["$$", "$$"], ["\\[", "\\]"]],
>           "packages": {"[+]": ["mhchem"]}
>         }
>       }'>
>   </script>
> ```


> 2. To include mermaid renderer copy the following into the head(or body) tag of your html
> ```
> <script type="module">
>       import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
>       mermaid.initialize({ startOnLoad: false }); // Prevent automatic rendering
>       document.addEventListener('DOMContentLoaded', function() {
>           // Find all code blocks with class 'mermaid'
>           const mermaidBlocks = document.querySelectorAll('pre code.language-mermaid');
>           mermaidBlocks.forEach(block => {
>               const code = block.textContent; // Get the content of the code block
>               const mermaidDiv = document.createElement('div');
>               mermaidDiv.classList.add('mermaid');
>               mermaidDiv.textContent = code; // Set the content to the div
>               block.parentNode.replaceChild(mermaidDiv, block); // Replace code block with div
>           });
>           mermaid.init(); // Render all mermaid diagrams
>       });
>   </script>
    

## Explanation and Example

Here we have included the Mathjax javascript library which can render math formulae and chemical equations.
TeX is a typesetting system that is widely used for mathematical and scientific documents.  
It allows you to create complex mathematical expressions, symbols, and equations with minimal effort.  

MathJax supports TeX syntax, allowing for dynamic rendering of math content in web pages. 
By configuring MathJax, you can customize how equations are displayed,
including support for inline or block-level formulas and chemical notation through the `mhchem` package.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MathJax with $$ for Math and Mermaid</title>
    <script type="text/javascript" async
        src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"
        id="MathJax-script"
        data-mathjax-config='{
          "loader": {
            "load": ["[tex]/mhchem"]
          },
          "tex": {
            "inlineMath": [["$", "$"], ["\\(", "\\)"]],
            "displayMath": [["$$", "$$"], ["\\[", "\\]"]],
            "packages": {"[+]": ["mhchem"]}
          }
        }'>
    </script>
    <!-- Include the Mermaid library -->
    <script type="module">
        import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
        mermaid.initialize({ startOnLoad: false }); // Prevent automatic rendering
        document.addEventListener('DOMContentLoaded', function() {
            // Find all code blocks with class 'mermaid'
            const mermaidBlocks = document.querySelectorAll('pre code.language-mermaid');
            mermaidBlocks.forEach(block => {
                const code = block.textContent; // Get the content of the code block
                const mermaidDiv = document.createElement('div');
                mermaidDiv.classList.add('mermaid');
                mermaidDiv.textContent = code; // Set the content to the div
                block.parentNode.replaceChild(mermaidDiv, block); // Replace code block with div
            });
            mermaid.init(); // Render all mermaid diagrams
        });
    </script>
</head>
<body>
    <h1>MathJax with $$ for Math and Chemistry</h1>

    <!-- Example of an Inline Math Formula -->
    <p>
        Inline math formula: $E = mc^2$
    </p>

    <!-- Example of a Block-Level Math Formula -->
    <p>
        Block-level math formula:
    </p>
    <p>
        $$ \int_0^1 x^2 \, dx = \frac{1}{3} $$
    </p>

    <!-- Example of a Chemical Equation -->
    <p>
        Here is a chemical equation: $ \ce{2H2 + O2 -> 2H2O} $
    </p>

    <!-- Example of a Block-Level Chemical Equation -->
    <p>
        Block-level chemical equation:
    </p>
    <p>
        $$ \ce{CH4 + 2O2 -> CO2 + 2H2O} $$
    </p>

    <!-- Example of a Mermaid Diagram in a Code Block -->
    <pre><code class="language-mermaid">
        graph TD;
        A[Start] --> B{Is it working?};
        B -- Yes --> C[Great!];
        B -- No --> D[Check the code];
    </code></pre>

</body>
</html>
```
