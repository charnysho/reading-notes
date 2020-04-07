## SMACSS and Responsive Web Design

### Responsive Web Design

   Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop. 

1. Responsive vs. Adaptive vs. Mobile

  - Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change.
  - Mobile, on the other hand, generally means to build a separate website commonly on a new domain solely for mobile users.

2. Flexible Layouts `#flexible-layouts`
 
   - Flexible grids are built using relative length units, most commonly percentages or em units. These relative lengths are then used to declare common grid property values such as `width`, `margin`, or `padding`.
   - Flexible layouts do not advocate the use of fixed measurement units, such as pixels or inches.

3. Flexible Grid

4. Media Queries `#media-queries`
   - Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example. 
   - `@media`
   - logical operators:  and, not, and only.
   - features: Height & Width
   - `orientation` media feature determines if a device is in the landscape or portrait orientation.
   - aspect-ratio and device-aspect-ratio features specifies the width/height pixel ratio of the targeted rendering area or output device. 
   - resolution media feature specifies the resolution of the output device in pixel density, also known as dots per inch or DPI. 

5. Mobile First
   - The mobile first approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.


### All About Floats

1. What is “Float”?
   - Floated elements remain a part of the flow of the web page. 

2. What are floats used for?
   - used to create entire web layouts.

3. Clearing the Float
   - An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.
   - Clear has four valid values: Both, Left, Right, None, Inherit(not supported in Internet Explorer)

4. The Great Collapse
   - floats can affect the element that contains them (their “parent” element)
   - Collapsing almost always needs to be dealt with to prevent strange layout and cross-browser problems. We fix it by clearing the float after the floated elements in the container but before the close of the container.

5. Techniques for Clearing Floats
   - The Empty Div Method `<div style="clear: both;"></div>`
   - The Overflow Method
   - The Easy Clearing Method uses a clever CSS pseudo selector (:after) 

6. Problems with Floats
   - Pushdown is a symptom of an element inside a floated item being wider than the float itself (typically an image). Quick fix: Make sure you don’t have any images that do this, use overflow: hidden to cut off excess.
   - Double Margin Bug – Another thing to remember when dealing with IE 6 is that if you apply a margin in the same direction as the float, it will double the margin. Quick fix: set display: inline on the float, and don’t worry it will remain a block-level element.
   - The 3px Jog is when text that is up next to a floated element is mysteriously kicked away by 3px like a weird forcefield around the float. Quick fix: set a width or height on the affected text.
   - In IE 7, the Bottom Margin Bug is when if a floated parent has floated children inside it, bottom margin on those children is ignored by the parent. Quick fix: using bottom padding on the parent instead.


### Don’t Overthink It Grids

1. Context
   - A block level element is as wide as the parent it’s inside (width: auto;). 

2. Columns

```
<div class="grid">
  <div class="col-2-3">
     Main Content
  </div>
  <div class="col-1-3">
     Sidebar
  </div>
</div>
```

```
[class*='col-'] {
  float: left;
}

.col-2-3 {
  width: 66.66%;
}
.col-1-3 {
  width: 33.33%;
}
```

3. Clearing Context

```
.grid:after {
  content: "";
  display: table;
  clear: both;
}
```

4. Gutters

   - The first step toward this is using box-sizing: border-box;. I like using it on absolutely everything.

```
*, *:after, *:before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
```

   - The second step is applying a fixed padding to the right side of all columns except the last one.

```
[class*='col-'] {
  padding-right: 20px;
}
[class*='col-']:last-of-type {
  padding-right: 0;
}
```

5. Outside Gutters

```
<div class="grid grid-pad">
  Grid with outside gutters also
</div>
```

- Step one is to add left padding to the grid parent (and optionally top and bottom padding):

```
.grid-pad {
  padding: 20px 0 20px 20px;
}
```

- Step two is to restore the right padding to the last column:

```
.grid-pad > [class*='col-']:last-of-type {
  padding-right: 20px;
}
```

6. More Column Choices

```
.col-1-2 {
  width: 50%;
}
.col-1-4 {
  width: 25%;
}
.col-1-8 {
  width: 12.5%;
}
```

7. Sass

```
* {
  @include box-sizing(border-box);
}

$pad: 20px;

.grid {
  background: white;
  margin: 0 0 $pad 0;
  
  &:after {
    /* Or @extend clearfix */
    content: "";
    display: table;
    clear: both;
  }
}

[class*='col-'] {
  float: left;
  padding-right: $pad;
  .grid &:last-of-type {
    padding-right: 0;
  }
}
.col-2-3 {
  width: 66.66%;
}
.col-1-3 {
  width: 33.33%;
}
.col-1-2 {
  width: 50%;
}
.col-1-4 {
  width: 25%;
}
.col-1-8 {
  width: 12.5%;
}

/* Opt-in outside padding */
.grid-pad {
  padding: $pad 0 $pad $pad;
  [class*='col-']:last-of-type {
    padding-right: $pad;
  }
}
```

8. Modules

```
<div class="grid">
  <div class="col-2-3">
     <article class="module">
        stuff
     </article>
     <article class="module">
        stuff
     </article>
  </div>
  <div class="col-1-3">
    <aside class="module">
       Sidebar stuff. Sub modules?
    </aside>
  </div>
</div>
```

### SMACSS

    - SMACSS is more style guide than rigid framework. SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process.
