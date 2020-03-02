## Introductory [HTML](#html) and [JavaScript](#javascript)

### HTML

1. Introduction
   - **Web browser** is an application used to access and view websites.
   - **Web server** is a computer which hosts the web site.
   - **Screen readers** are programs that read out the contents of a computer screen to a user.
   - <img src="https://d1o2okarmduwny.cloudfront.net/wp-content/uploads/2015/07/how-dns-works.jpg" alt="drawing" width="300"/>

2. Structure 
   - **HTML** describes the structure of pages.<br>
   ```
    <html> 
        <head>
            <title>This is the Title of the page</title>
        </head>
        <body>
            <h1>The Main Heading</h1>
            <p>Paragraph</p>
            <h2>Sub-heading</h2>
            <p>Another paragraph</p>
        </body>
    </html>
    ```
    `html` tag tells the browser that this is an HTML document.<br>
    `head` tag contains information *about* the page.<br>
    `body` tag defines the document's body.
    - **Attributes** provide additional information about HTML elements.They usually come in name/value pairs like: name="value".
    ```
    <img src="test.jpg">
    ```
    
3. Extra Markup
   - **DOCTYPES** tell browsers which version of HTML you are using.
   - **Comments** in HTML 
    ```
    <!-- comment -->
    ```
    - The `id` and `class` attributes allow you to identify particular elements.<br>
    *Note*: an HTML element can only have one unique id that belongs to that single element, while a class name can be used by multiple elements.
    ```
    <!-- A unique element -->
    <h1 id="myHeader">My Cities</h1>

    <!-- Multiple similar elements -->
    <h2 class="city">London</h2>
    <p>London is the capital of England.</p>

    <h2 class="city">Paris</h2>
    <p>Paris is the capital of France.</p>
    ```
    - The `div` and `span` elements allow you to group block-level(`h1`,  `p`, `ul`, `li`) and inline(`a`, `b` `em`, `img`) elements together.
    - `iframe` is used to display a web page within a web page.
    ```
    <iframe src="demo_iframe.htm" height="200" width="300"></iframe>
    ```
    - `meta` tag allows you to supply all kinds of information about your web page.
    ```
    <head>
        <meta charset="UTF-8">
        <meta name="description" content="Free Web tutorials">
        <meta name="keywords" content="HTML,CSS,XML,JavaScript">
        <meta name="author" content="John Doe">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    ```
    - Escape characters are used to include special characters in your pages such as <, > and ®.

4. HTML5 Layout
   - `header` element represents a container for introductory content or a set of navigational links. `article` tag specifies independent, self-contained content(forum post, blog post, news story).
    ```
    <article>
        <header>
            <h1>Most important heading here</h1>
            <h2>Less important heading here</h2>
            <p>Some additional information here</p>
        </header>
        <p>Lorem Ipsum dolor set amet....</p>
    </article>
    ```
    - `footer` tag defines a footer for a document or section.
    ```
    <footer>
        <p>Posted by: Hege Refsnes</p>
        <p>Contact information: <a href="mailto:someone@example.com">
        someone@example.com</a>.</p>
    </footer>
    ```
    - `nav` tag defines a set of navigation links.
     ```
    <nav>
        <a href="/html/">HTML</a> |
        <a href="/css/">CSS</a> |
        <a href="/js/">JavaScript</a> |
    </nav>
    ```
    - `aside` tag defines some content aside from the content it is placed in.
    ```
    <p>My family and I visited The Epcot center this summer.</p>
    
    <aside>
    <h4>Epcot Center</h4>
    <p>Epcot is a theme park at Walt Disney World Resort.</p>
    </aside>
    ```
    - `hgroup` tag is used to group the heading elements. 
    ```
    <hgroup> 
        <h1>This is the title.</h1> 
        <h2>This is sub-title.</h2> 
    </hgroup>
    ```
    - `figure` tag specifies self-contained content, like illustrations, diagrams, photos, code listings, etc. `figcaption` element is used to add a caption for the `figure` element.
    ```
    <figure>
        <img src="pic_trulli.jpg" alt="Trulli" style="width:100%">
        <figcaption>Fig.1 - Trulli, Puglia, Italy.</figcaption>
    </figure>
    ```
    - Older browsers that do not understand HTML5 elements neet to be told which elements are block-level elements.

5. Process & Design
   - **Who** is the site for:
     - Individuals
     - Companies
    - **Why** people visit your website:
      - Key motivation
      - Specific goals
    - **What** your visitors are trying to achieve
      - Key tasks
    - **What** information your visitors need
      - Key information
    - **How often** people will visit your site
      - Goods/Services
      - Information
    - **Site maps** allow you to plan the structure of a site.
    - **Wireframes** allow you to organize the information that will need to go on each page. 
    - **Design** is about communication.
      - Content
      - Prioritizing
      - Orginizing
      - Visual hierarchy 
        - Size
        - Color
        - Style
        - Images
      - Grouping
        - Proximity
        - Closure
        - Continuance
        - White space
        - Color
        - Borders
      - Similarity
        - Consistency
        - Headings
    - **Designing navigation**
      - Concise
      - Clear
      - Selective
      - Contex
      - Interactive
      - Consistent


### JavaScript

1. Introduction
   - How JavaScript makes web pages more interactive:
     - Access content
     - Modify content
     - Program rules 
     - React to events
   - Examples of JS in the browser
     - Forms
     - Slideshows
     - Reload part of page
     - Filtering data

2. The ABC of Programming
   - The **script** is a series of instruction.
   - **Objects** are containers for named values called properties or methods.
     - Properties (name+value)
     - Events are "things" that happen to HTML elements.
     - Methods are actions that can be performed on objects.
   - How the browser sees a web page:
     - The browser receives an HTML page
     - It creates a model of the page and stores it in memory
     - It shows the page on screen using a rendering engine.
   - How HTML, CSS, JS fit together:
     - HTML(content layer)
     - CSS(presentation layer)
     - JS(behavior layer)
   - How to use Object & Method:
    ```
    document.write('Hello world!');
    ```
    Where document is an object and write() is a method.
   - `script` tag is used to define a client-side script (JavaScript). `src` attribute specifies the URL of an external script file.
   ``` 
   <script src="myscripts.js"></script>
   ```
 

