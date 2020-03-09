## [JS Object](#js-objects) Literals; The [DOM](#dom)

### JS Object

Object group together a set of var and func to create a model of smth you would recognize from the real world.

```
var hotel = {
  name: "Quay", // properties
  rooms: "40",
  booked: "25",
  checkAvailability: function() {       // method
    return this.rooms - this.booked; 
  }
};


var hotelName = hotel.name;
var roomsFree = hotel.checkAvailability();

or

var hotelName = hotel['name'];
var roomsFree = hotel['checkAvailability']();
```

### DOM

The DOM tree is a model of a WEB page. It is srored in the browser's memory.
Accessing and updating the DOM tree involves 2 steps:
- Locate the node that represents the element you want to work with 
- Use its text content, child elements, and attributes.

- Finding HTML elements by id

```
var myElement = document.getElementById("intro");
```

- Finding HTML elements by tag name

```
var x = document.getElementsByTagName("p");
```

- Finding HTML elements by class name

```
var x = document.getElementsByClassName("intro");
```

- Finding HTML elements by CSS selectors

```
var x = document.querySelectorAll("p.intro");
```

- Finding HTML elements by HTML object collections

```
var x = document.forms["frm1"];
var text = "";
var i;
for (i = 0; i < x.length; i++) {
  text += x.elements[i].value + "<br>";
}
document.getElementById("demo").innerHTML = text;
```

A `NodeList` object is a list (collection) of nodes extracted from a document.
All browsers return a NodeList object for the property `childNodes`. 

```
//repeating actions for an entire nodelist
var hotItems = document.querySelectorAll('li.hot');
for(var i = 0; i < hotItems.lenght; i++) {
  hotItems[i].className = 'cool';
}
```

```
//Attribute nodes
document.getElementById('one').getAttribute('class');
```

The `encodeURIComponent()` function encodes a URI component. This function encodes special characters. In addition, it encodes the following characters: , / ? : @ & = + $ #

```
This function encodes special characters. In addition, it encodes the following characters: , / ? : @ & = + $ #
```
