## [HTML Tables](#html-tables); [JS Constructor Functions](#js-constructor-functions)

### HTML Tables
- A table represents information in a grid format.
- An HTML table is defined with the `<table>` tag.
- Each table row is defined with the `<tr>` tag. A table header is defined with the `<th>` tag. By default, table headings are bold and centered. A table data/cell is defined with the `<td>` tag.

```
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th> 
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td> 
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td> 
    <td>94</td>
  </tr>
</table>
```

- Use the `colspan` attribute to make a cell span many columns
- Use the `rowspan` attribute to make a cell span many rows

- The `<thead>` tag is used to group header content in an HTML table.
- The `<thead>` element is used in conjunction with the `<tbody>` and `<tfoot>` elements to specify each part of a table (header, body, footer).

```
<table>
  <thead>
    <tr>
      <th>Month</th>
      <th>Savings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>$100</td>
    </tr>
    <tr>
      <td>February</td>
      <td>$80</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sum</td>
      <td>$180</td>
    </tr>
  </tfoot>
</table>
```


### JS Constructor Functions

- Constructor notation

```
//creates a blank object
var hotel = new Object();

//updating an object
hotel.name = 'Park';
or
hotel['name'] = 'Park';
```

- Creating many objects

```
function Hotel(name, rooms) {
   this.name = name;
   this.rooms = rooms;
   this.booked = booked;
   this.checkAvailability = function() {
     return this.room - this.booked;
   }
}


var parkHotel = new Hotel('Park', '120', '77');
```

- Arrays are a special type of object.
- Arrays can be inside the object 
- Objects can be inside the arrays

- Groups of built-in objects:
  - Browser object model
    - The `window` object is supported by all browsers. It represents the browser's window.
    
    ```
    window.document.getElementById("header");
    or
    document.getElementById("header");
    ```
    Properties:
    - `window.innerHeight`
    - `window.innerWidth`
    - `window.open()`
    - `window.close()`
  - Document object model
    - <img src="https://www.w3schools.com/js/pic_htmltree.gif" alt="drawing" width="300"/>
    - The HTML DOM model is constructed as a tree of Objects:
  - Global JS objects
    - The global object provides variables and functions that are available anywhere. By default, those that are built into the language or the environment.
    - The global object itself can be accessed using the this operator in the global scope. In fact, the global scope consists of the properties of the global object, including inherited properties, if any.
    - Value properties
      - `Infinity`
      - `NaN`
      - `undefined`
      - `globalThis`
    - Function properties
      - `parseInt()`
      - `isNaN()`
    - Fundamental objects
      - `Object`
      - `Function`
      - `Boolean`
      - `Symbol`
    - Numbers and dates
      - `Number`
      - `Math`
      - `Date`
    


