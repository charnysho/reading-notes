## [Forms](#forms) and [Events](#events)


### Forms
1. Forms
   - Forms control 
     - adding text
     - making choices
     - submitting forms
     - iploading files
   - How forms workk:
     - a user fills in a form and then presses a button to submit the information to the server
   - Form structure `form`
   - Text inpit `input`
   - Text area `textarea`
   - radio button `type='radio'`
   - checkbox `type='checkbox'`
   - drop down list box `<select>`, `<option>`
   - file input box `type='file'`
   - submit button `type='submit'`
   - email and url input `type='email'`, `type='url'`
   - search `type='search'`

2. Lists, Tables & Forms
   - bullet point style `list-style-type`
   - images for bullets `list-style-image`
   - positioning the marker `list-style-position`
   - list shorthand `list-style`

   Table properties:
   - width
   - padding
   - text-transform
   - letter-spacing? font-size
   - border-top, border-bottom
   - text-align
   - background color
   - :hover

   Border on empty cell `empty-cells`
   Gaps between cells `border-spacing, border-collapse`

      
### Events

1. User Interface events
   - load (The load event fires when the webpage finishes loading. It can also fire on nodes of elements like images, scripts, or objects.)
   - error (This event fires when the browser encounters a JavaScript error or an asset that doesn’t exist.)
   - scroll (This event fires when the user scrolls up/down on the browser window. It can relate to the entire page or a specific element on the page.)

2. Focus and blur events
   - focus (This event fires, for a specific DOM node, when an element gains focus.)

3. Mouse events
   - click (This event fires when the user clicks on the primary mouse button (usually the left button). This event also fires if the user presses the Enter key on the keyboard when an element has focus.)
   - mouseover (It fires when the user moves the cursor, which was outside an element before, inside the element. We can say that it fires when we move the cursor over the element.)

4. Keyboard events
   - input (This event fires when the value of an <input> or a <textarea> changes (doesn’t fire for deleting in IE9). You can use keydown as a fallback in older browsers.)
   - keypress (It fires when the user presses a key that results in printing a character on the screen. This event fires repeatedly if the user holds down the key. This event will not fire for the enter, tab, or arrow keys; the keydown event would.)

5. Form events
   - submit (This event fires on the node representing the <form> element when a user submits a form.)
   - input (The input event is very common with the <input> and the <textarea> elements.)

#### DOM event handlers

```
element.oneevent = functionName;
```

1. The `addEventListener()` method attaches an event handler to the specified element.
The addEventListener() method attaches an event handler to an element without overwriting existing event handlers.

```
document.getElementById("myBtn").addEventListener("click", displayDate);
```

2. Add an Event Handler to an Element

```
element.addEventListener("click", function(){ alert("Hello World!"); });
```

3. Add Many Event Handlers to the Same Element

```
element.addEventListener("click", myFunction);
element.addEventListener("click", mySecondFunction);
```

4. Add an Event Handler to the window Object

```
window.addEventListener("resize", function(){
  document.getElementById("demo").innerHTML = sometext;
});
```

5. Passing Parameters

```
element.addEventListener("click", function(){ myFunction(p1, p2); });
```

6. The removeEventListener() method

```
element.removeEventListener("mousemove", myFunction);
```

#### Event Object
 
 - bubbles (Returns whether or not a specific event is a bubbling event)
 - createEvent() (Creates a new event)
 - type (Returns the name of the event)

 #### Event Types
 
 - abort (The event occurs when the loading of a media is aborted)
 - error (The event occurs when an error occurs while loading an external file)
 - load (The event occurs when an object has loaded)
 - open (The event occurs when a connection with the event source is opened)
 - play (The event occurs when the media has been started or is no longer paused)
 - scroll (The event occurs when an element's scrollbar is being scrolled)