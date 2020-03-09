## [HTML text](#html-text), [CSS](#css) Introduction, and Basic [#JavaScript](javascript) Instructions

### HTML text

| Tag        | Example           | Definition  |
| ------------- |:-------------:| -----:|
| Headings      | `<h1></h1>` |  |
| Paragraphs      | `<p></p>`     |    |
| Bold | `<b></b>`      |     |
| Italic | `<i></i>`      |     |
| Superscript | `<p>This text contains <sup>superscript</sup> text.</p>`      | Superscript text appears half a character above the normal line, and is sometimes rendered in a smaller font.    |
| Subscript | `<sub></sub>`      | Subscript text appears half a character below the normal line, and is sometimes rendered in a smaller font.    |
| Line breaks | `<br/>`      |     |
| Horizontal rule | `<hr/>`      | thematic break in an HTML page, used to separate content    |
| Strong | `<strong></strong>`      | It defines important text.    |
| Emphasis | `<em></em>`      | The contents of this element in italic    |
| Blockquote | `<blockquote></blockquote>`      | Specifies a section that is quoted from another source.   |
| Q | `<q></q>`      | Defines a short quotation    |
| Abbreviations & Acronyms      | `The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.`     | Defines an abbreviation or an acronym, like "HTML", "Mr.", "Dec.", "ASAP", "ATM".   |
| Citations | `<p><cite>The Scream</cite> by Edward Munch. Painted in 1893.</p>`      | defines the title of a work     |
| Definitions | `<p><dfn>HTML</dfn> is the standard markup language for creating web pages.</p>`      | Represents the defining instance of a term in HTML.  |
| Author details      | `<address></address>` | Defines the contact information for the author/owner of a document or an article. |
| Changes to content      | `<p>My favorite color is <del>blue</del> <ins>red</ins>!</p>` | Defines a text that has been inserted into a document.  |
| Changes to content      | `<p>My favorite color is <del>blue</del> <ins>red</ins>!</p>` | Defines text that has been deleted from a document.  |
| Changes to content      | `<p><s>My car is blue.</s></p>` | specifies text that is no longer correct, accurate or relevant. |


### CSS

<img src="https://i.pinimg.com/originals/5d/7a/82/5d7a82064300f646c963998ebb22ff70.gif" alt="drawing" width="300"/>

1. External CSS
External styles are defined within the `<link>` element, inside the `<head>` section of an HTML page:

  ```
  <html>
      <head>
        <link rel="stylesheet" type="text/css" href="mystyle.css">
      </head>
      <body>

        <h1>This is a heading</h1>
        <p>This is a paragraph.</p>

      </body>
  </html>
  ```

2. Internal CSS
Internal styles are defined within the `<style>` element, inside the `<head>` section of an HTML page:

  ```
  <head>
    <style>
    body {
      background-color: linen;
    }

    h1 {
      color: maroon;
      margin-left: 40px;
    } 
    </style>
  </head>
  ```

3. CSS selectors are patterns used to select the element(s) you want to style.
  <img src="selectors.jpg" alt="drawing" width="300"/>
  

### JavaScript

1. Statement 
A computer program is a list of "instructions" to be "executed" by a computer.
In a programming language, these programming instructions are called **statements**.

2. Comments

```
// Change paragraph:
```

or

```
/*
Comment
*/
```

3. Variable are containers for storing data values.
<img src="https://tutorial.techaltum.com/images/js-variables.jpg" alt="drawing" width="300"/>

4. Data types
<img src="https://dotnettrickscloud.blob.core.windows.net/img/javascript/js-datatype.png" alt="drawing" width="300"/>

5. Arrays are used to store multiple values in a single variable.

```
var array_name = [item1, item2, ...];
```

6. Expression 
   - assign a value to a variable

   ```
   var color = 'black';
   ```

   - use to or more values to return a single value

   ```
   var area = 3 * 2;
   ```

7. Operators
      - Assignment

      ```
      var x = 10;
      ```

      - Adding

      ```
      var x = 5;
      var y = 2;
      var z = x + y;
      ```

      - Multiplying

      ```
      var x = 5;
      var y = 2;
      var z = x * y;
      ```

      - String operator

      ```
      greeting = 'Hi' + 'Molly'
      ```

      - Comparison

      ```
      buy = 3 > 5;
      ```

      - Logical

      ```
      buy = (5 > 3) && (2 < 4);
      ```

10. Conditional Statements (when you want to perform different actions for different decisions)

```
if (condition) {
  //  block of code to be executed if the condition is true
} else { 
  //  block of code to be executed if the condition is false
}
```

9. Comparison operators
<img src="https://www.miltonmarketing.com/wp-content/uploads/2018/04/javascriptcomparisonoperatorsimage041.jpg" alt="drawing" width="300"/>

10. Logical operators
<img src="https://www.bccfalna.com/ebooks/wp-content/uploads/ebooks/2019/08/Boolean-Operators-Logical-AND-Logical-OR-Logical-NOT-in-JavaScript-in-Hindi-580x435.jpg" alt="drawing" width="300"/>

11. `if` statement
    - `if` statement to specify a block of JavaScript code to be executed if a condition is true.

    ```
    if (condition) {
    //  block of code to be executed if the condition is true
    }
    ```

    - `if else` statement to specify a block of code to be executed if the condition is false.

    ```
    if (condition) {
    //  block of code to be executed if the condition is true
    } else { 
    //  block of code to be executed if the condition is false
    }
    ```




