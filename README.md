# How to render chemical and mathematical equations

## Prerequisites
1. Have an HTML file.

## Steps
1. Include mathjax cdn(Content Delivery Network)
2. Set up the tex engine to render text enclosed in required characters.

## Example Code

Here we have included the Mathjax javascript library which is capable of rendering both math formulae and chemical equations.
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
    <title>MathJax with $$ for Math</title>
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

</body>
</html>
```
