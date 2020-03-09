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

```
document.getElementById('one'); //select individual element
```

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
