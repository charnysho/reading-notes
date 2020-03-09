## [HTML](#html) Images; [CSS](#css) Color & Text

### HTML

1. Images 

```
<img src="smiley.gif" alt="Smiley face" height="42" width="42">
```

2. You must always specify an src attribute to indicate the source of an image and an alt attribute to describe the content of an image.

3. You should save image at the size you will be using them on the web page and in the appropriate format.

4. Photo are best saved as JPEGs; illustrations or logos that use flat colors are better saved as GIFs.

### CSS

1. Color

```
body {
  color: red;
}

h1 {
  color: #00ff00;
}

p.ex {
  color: rgb(0,0,255);
}
```

2. Background-color

```
body {background-color: coral;}
```

3. Text
   - serif
   - sans-serif
   - monospace
   - weight
   - style
   - stretch

4. The font-family property specifies the font for an element.

```
p.a {
  font-family: "Times New Roman", Times, serif;
}

p.b {
  font-family: Arial, Helvetica, sans-serif;
}
```

5. The font-size property sets the size of a font.

```
div.a {
  font-size: 15px;
}

div.b {
  font-size: large;
}

div.c {
  font-size: 150%;
}
```