## Docs for the HTML <canvas> Element & Chart.js

### Chart.js

- Chart.js is a JavaScript library that allows you to draw different types of charts by using the HTML5 `canvas` element.
- Chart.js is that the charts are responsive, so they will adapt based on the space available.

1. Installation

You can download the latest version of Chart.js from the GitHub releases or use a Chart.js CDN. Detailed installation instructions can be found on the installation page.

2. Creating a Chart

```
<canvas id="myChart" width="400" height="400"></canvas>
<script>
var ctx = document.getElementById('myChart').getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                }
            }]
        }
    }
});
</script>
```

### Basic usage of canvas

1. The `<canvas>` element (has only two attributes, width and height). The `<canvas>` element can be styled just like any normal image (margin, border, background…).

```
<canvas id="tutorial" width="150" height="150"></canvas>
```

2. Fallback content

```
<canvas id="stockGraph" width="150" height="150">
  current stock price: $3.15 + 0.15
</canvas>

<canvas id="clock" width="150" height="150">
  <img src="images/clock.png" width="150" height="150" alt=""/>
</canvas>
```

3. The rendering context. The `<canvas>` element has a method called getContext(), used to obtain the rendering context and its drawing functions.

```
var canvas = document.getElementById('tutorial');
var ctx = canvas.getContext('2d');
```

4. Checking for support

```
var canvas = document.getElementById('tutorial');

if (canvas.getContext) {
  var ctx = canvas.getContext('2d');
  // drawing code here
} else {
  // canvas-unsupported code here
}
```

### Drawing shapes with canvas

1. Drawing rectangles

`fillRect(x, y, width, height)` Draws a filled rectangle.
`strokeRect(x, y, width, height)` Draws a rectangular outline.
`clearRect(x, y, width, height)` Clears the specified rectangular area, making it fully transparent.

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100);
    ctx.clearRect(45, 45, 60, 60);
    ctx.strokeRect(50, 50, 50, 50);
  }
}
```

`fillRect()` function draws a large black square 100 pixels on each side
`clearRect()` function then erases a 60x60 pixel square from the center
`strokeRect()` is called to create a rectangular outline 50x50 pixels within the cleared square

2. Drawing paths
   1. First, you create the path.
   2. Then you use drawing commands to draw into the path.
   3. Once the path has been created, you can stroke or fill the path to render it.

`beginPath()` Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
`Path methods` Methods to set different paths for objects.
`closePath()` Adds a straight line to the path, going to the start of the current sub-path.
`stroke()` Draws the shape by stroking its outline.
`fill()` Draws a solid shape by filling the path's content area.

3. Drawing a triangle

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

4. Moving the pen

`moveTo(x, y)` Moves the pen to the coordinates specified by x and y.

5. Lines

`lineTo(x, y)` Draws a line from the current drawing position to the position specified by x and y.

6. Arcs

`arc(x, y, radius, startAngle, endAngle, anticlockwise)`
Draws an arc which is centered at (x, y) position with radius r starting at startAngle and ending at endAngle going in the given direction indicated by anticlockwise (defaulting to clockwise).
`arcTo(x1, y1, x2, y2, radius)`
Draws an arc with the given control points and radius, connected to the previous point by a straight line.

7. Bezier and quadratic curves

`quadraticCurveTo(cp1x, cp1y, x, y)`
Draws a quadratic Bézier curve from the current pen position to the end point specified by x and y, using the control point specified by cp1x and cp1y.
`bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)`
Draws a cubic Bézier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).

8. Rectangles

`rect(x, y, width, height)`
Draws a rectangle whose top-left corner is specified by (x, y) with the specified width and height.

### Path2D objects

`Path2D()`
The Path2D() constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.

```
new Path2D();     // empty path object
new Path2D(path); // copy from another Path2D object
new Path2D(d);    // path from SVG path data
```

`Path2D.addPath(path [, transform])`
Adds a path to the current path with an optional transformation matrix.

```
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    var rectangle = new Path2D();
    rectangle.rect(10, 10, 50, 50);

    var circle = new Path2D();
    circle.moveTo(125, 35);
    circle.arc(100, 35, 25, 0, 2 * Math.PI);

    ctx.stroke(rectangle);
    ctx.fill(circle);
  }
}
```

- Using SVG paths

Another powerful feature of the new canvas Path2D API is using SVG path data to initialize paths on your canvas. This might allow you to pass around path data and re-use them in both, SVG and canvas.
The path will move to point (M10 10) and then move horizontally 80 points to the right (h 80), then 80 points down (v 80), then 80 points to the left (h -80), and then back to the start (z). You can see this example on the Path2D constructor page.

```
var p = new Path2D('M10 10 h 80 v 80 h -80 Z');
```

### Applying styles and colors

1. Colors

`fillStyle = color`
Sets the style used when filling shapes.
`strokeStyle = color`
Sets the style for shapes' outlines.

```
// these all set the fillStyle to 'orange'

ctx.fillStyle = 'orange';
ctx.fillStyle = '#FFA500';
ctx.fillStyle = 'rgb(255, 165, 0)';
ctx.fillStyle = 'rgba(255, 165, 0, 1)';
```

2. Transparency

`globalAlpha = transparencyValue`
Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (fully transparent) to 1.0 (fully opaque). This value is 1.0 (fully opaque) by default.

```
// Assigning transparent colors to stroke and fill style

ctx.strokeStyle = 'rgba(255, 0, 0, 0.5)';
ctx.fillStyle = 'rgba(255, 0, 0, 0.5)';
```

3. Line styles

`lineWidth = value`
Sets the width of lines drawn in the future.
`lineCap = type`
Sets the appearance of the ends of lines.
`lineJoin = type`
Sets the appearance of the "corners" where lines meet.
`miterLimit = value`
Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
`getLineDash()`
Returns the current line dash pattern array containing an even number of non-negative numbers.
`setLineDash(segments)`
Sets the current line dash pattern.
`lineDashOffset = value`
Specifies where to start a dash array on a line.

4. Gradients

`createLinearGradient(x1, y1, x2, y2)`
Creates a linear gradient object with a starting point of (x1, y1) and an end point of (x2, y2).
`createRadialGradient(x1, y1, r1, x2, y2, r2)`
Creates a radial gradient. The parameters represent two circles, one with its center at (x1, y1) and a radius of r1, and the other with its center at (x2, y2) with a radius of r2.

```
var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
var radialgradient = ctx.createRadialGradient(75, 75, 0, 75, 75, 100);
```

`gradient.addColorStop(position, color)`
Creates a new color stop on the gradient object. The position is a number between 0.0 and 1.0 and defines the relative position of the color in the gradient, and the color argument must be a string representing a CSS <color>, indicating the color the gradient should reach at that offset into the transition.

```
var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
lineargradient.addColorStop(0, 'white');
lineargradient.addColorStop(1, 'black');
```

5. Patterns

`createPattern(image, type)`
Creates and returns a new canvas pattern object. image is a CanvasImageSource (that is, an HTMLImageElement, another canvas, a <video> element, or the like. type is a string indicating how to use the image.

`repeat`
Tiles the image in both vertical and horizontal directions.
`repeat-x`
Tiles the image horizontally but not vertically.
`repeat-y`
Tiles the image vertically but not horizontally.
`no-repeat`
Doesn't tile the image. It's used only once.

6. Shadows

`shadowOffsetX = float`
Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
`shadowOffsetY = float`
Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
`shadowBlur = float`
Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.
`shadowColor = color`
A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

7. Canvas fill rules

When using `fill` (or clip and isPointinPath) you can optionally provide a fill rule algorithm by which to determine if a point is inside or outside a path and thus if it gets filled or not. This is useful when a path intersects itself or is nested.

Two values are possible:
- nonzero
- evenodd

```
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d'); 
  ctx.beginPath(); 
  ctx.arc(50, 50, 30, 0, Math.PI * 2, true);
  ctx.arc(50, 50, 15, 0, Math.PI * 2, true);
  ctx.fill('evenodd');
}
```

### Drawing text

1. Drawing text

`fillText(text, x, y [, maxWidth])`
Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
`strokeText(text, x, y [, maxWidth])`
Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.

```
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  ctx.font = '48px serif';
  ctx.fillText('Hello world', 10, 50);
}
```

2. Styling text

`font = value`
The current text style being used when drawing text. This string uses the same syntax as the CSS font property. The default font is 10px sans-serif.
`textAlign = value`
Text alignment setting. Possible values: start, end, left, right or center. The default value is start.
`textBaseline = value`
Baseline alignment setting. Possible values: top, hanging, middle, alphabetic, ideographic, bottom. The default value is alphabetic.
`direction = value`
Directionality. Possible values: ltr, rtl, inherit. The default value is inherit.

3. Advanced text measurements

`measureText()`
Returns a TextMetrics object containing the width, in pixels, that the specified text will be when drawn in the current text style.
