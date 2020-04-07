## jQuery, Events, and The DOM

### jQuery

- jQuery is a JS file that lets you find elements using CSS-style selectors and then do smth with the elements using jQuery methods.

1. Find elements using CSS-style selectors

   ```
   $('li.hot')
   ```

2. Do smth with the elements using jQuery methods.
   
   ```
   $('li.hot').addClass('complete');
   ```
   
3. Why use jQuery?
   - simple selectors
   - common tasks in less code
   - cross-browser compatibility

4. Finding elements:
   - basic selectors(*, element, #id ...)
   - hierarchy(parent > child, prev + next ...)
   - basic filters(:first, :last, :even ...)
   - content filters(:parent, :empty ...)
   - visibility filters(:hidden, :visible)
   - child filters(:first-child, :last-child...)
   - attribute filters([attribute]...)
   - form(:input, :text ...)

5. Doing things with your selection:
   - content filters
   - finding elements
   - dimension/positioning
   - effects&animation
   - events

6. Checking a page is ready to work with:

```
$(document).ready(function() {
  //script
})
```

7. Getting elements content:
   - .html()
   - .text()

8. Updating elements:
   - .replaceWith()
   - .remove()

9. Events
   - .change()
   - .click()
   - .error()
   - event.target

10. Effects:
    - animate()
    - show()
    - slideDown()
    - toggle()
  
11. Example: hide all <p> elements

```
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("p").hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me to hide paragraphs</button>

</body>
</html>
```