## CSS Transforms, Transitions, and Animations

### Transforms

The `transform` property comes in two different settings, two-dimensional and three-dimensional.

```css
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

1. 2D Rotate

The `rotate` value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically.

```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```css
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

2. 2D Scale

The default `scale` value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

```css
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

3. 2D Translate

Using the `translateX` value will change the position of an element on the horizontal axis while using the `translateY` value will change the position of an element on the vertical axis. As with the `scale` value, to set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```css
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

4. 2D Skew is used to distort elements on the horizontal axis, vertical axis, or both. Using the `skewX` value distorts an element on the horizontal axis while the `skewY` value distorts an element on the vertical axis. 

5. Combining Transforms. To combine transforms, list the transform values within the transform property one after the other without the use of commas.

6. Transform Origin. The default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the transform-origin property may be used.

```css
.box-1 {
  transform: rotate(15deg);
  transform-origin: 0 0;
}
.box-2 {
  transform: scale(.5);
  transform-origin: 100% 100%;
}
.box-3 {
  transform: skewX(20deg);
  transform-origin: top left;
}
.box-4 {
  transform: scale(.75) translate(-10px, -10px);
  transform-origin: 20px 50px;
}
```

7. Perspective

The example below shows a handful of elements all transformed using their individual perspectives with the perspective value.
```css
.box {
  transform: perspective(200px) rotateX(45deg);
}
```

8. Perspective Origin

The large difference between the two falls where the origin of a transform determines the coordinates used to calculate the change of a transform, while the origin of a perspective identifies the coordinates of the vanishing point of a transform.

```html
<div class="original original-1">
  <figure class="box">Box 1</figure>
</div>
<div class="original original-2">
  <figure class="box">Box 2</figure>
</div>
<div class="original original-3">
  <figure class="box">Box 3</figure>
</div>
```

```css
.original {
  perspective: 200px;
}
.box {
  transform: rotateX(45deg);
}
.original-1 {
  perspective-origin: 0 0;
}
.original-2 {
  perspective-origin: 75% 75%;
}
.original-3 {
  perspective-origin: 20px 40px;
}
```

9. 3D Rotate
Using the rotateX value allows you to rotate an element around the x axis, as if it were being bent in half horizontally. Using the rotateY value allows you to rotate an element around the y axis, as if it were being bent in half vertically. Lastly, using the rotateZ value allows an element to be rotated around the z axis.

```css
.box-1 {
  transform: perspective(200px) rotateX(45deg);
}
.box-2 {
  transform: perspective(200px) rotateY(45deg);
}
.box-3 {
  transform: perspective(200px) rotateZ(45deg);
}
```

10. 3D Scale. By using the scaleZ three-dimensional transform elements may be scaled on the z axis. 

11. 3D Translate. A negative value here will push an element further away on the z axis, resulting in a smaller element. Using a positive value will pull an element closer on the z axis, resulting in a larger element.

12. 3D Skew. Skew is the one two-dimensional transform that cannot be transformed on a three-dimensional scale. Elements may be skewed on the x and y axis, then transformed three-dimensionally as wished, but they cannot be skewed on the z axis.

13. Shorthand 3D. TransformsAs with combining two-dimensional transforms, there are also properties to write out shorthand three-dimensional transforms. These properties include rotate3d, scale3d, transition3d, and matrix3d.

14. Transform Style. To allow nested elements to transform in their own three-dimensional plane use the transform-style property with the preserve-3d value.

```html
<div class="rotate three-d">
  <figure class="box">Box 1</figure>
</div>
<div class="rotate">
  <figure class="box">Box 2</figure>
</div>
```

```css
.rotate {
  transform: perspective(200px) rotateY(45deg);
}
.three-d {
  transform-style: preserve-3d;
}
.box {
  transform: rotateX(15deg) translateZ(20px);
  transform-origin: 0 0;
}
```

15. Backface Visibility
    - not to see these elements `backface-visibility: hidden`
    - `backface-visibility: visible`

### Transitions & Animations

1. Transitions
   - `transition-property`
   - `transition-duration`
   - `transition-timing-function`
   - `transition-delay`

It is important to note, **not all properties may be transitioned**, only properties that have an identifiable halfway point.

2. The duration in which a transition takes place is set using the `transition-duration` property.

3. `transition-timing-function` property is used to set the speed in which a transition will move. 

4. On top of declaring the transition property, duration, and timing function, you can also set a delay with the `transition-delay` property.

5. `transition`, capable of supporting all of these different properties and values that was mention above.

6. Animations

To set multiple points at which an element should undergo a transition, use the `@keyframes` rule. The `@keyframes` rule includes the animation name, any animation breakpoints, and the properties intended to be animated.

```css
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```

7. `animation-name` property is used with the animation name, identified from the `@keyframes` rule, as the property value.

8. To start, animations need a duration declared using the `animation-duration` property. A timing function and delay can be declared using the `animation-timing-function` and `animation-delay` properties respectively. 

```css
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```

9. To have an animation repeat itself numerous times the `animation-iteration-count` property may be used.

10. On top of being able to set the number of times an animation repeats, you may also declare the direction an animation completes using the `animation-direction property`.

11. `animation-play-state` property allows an animation to be played or paused using the running and paused keyword values respectively. 

12. `animation-fill-mode property` identifies how an element should be styled either before, after, or before and after an animation is run. 

13. Shorthand Animations

```css
.stage:hover .ball {
  animation: slide 2s ease-in-out .5s infinite alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```

### 8 simple CSS3 transitions that will wow your users

1. Fade in

```css
.fade
{
        opacity:0.5;
}
.fade:hover
{
        opacity:1;
}
```

2. Change color

```css
.color:hover
{
        background:#53a7ea;
}
```

3. Grow & Shrink

```css
.grow:hover
{
        -webkit-transform: scale(1.3);
        -ms-transform: scale(1.3);
        transform: scale(1.3);
}
```

4. Rotate elements

```css
.rotate:hover
{
        -webkit-transform: rotateZ(-30deg);
        -ms-transform: rotateZ(-30deg);
        transform: rotateZ(-30deg);
}
```

5. Square to circle

```css
.circle:hover
{
        border-radius:50%;
}
```

6. 3D shadow

```css
.threed:hover
{
        box-shadow:
                1px 1px #53a7ea,
                2px 2px #53a7ea,
                3px 3px #53a7ea;
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
}
```

7. Swing

```css
@-webkit-keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
       transform: translateX(-5px);
    } 
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
```
8. Inset border

```css
.border:hover
{
        box-shadow: inset 0 0 0 25px #53a7ea;
}
```



