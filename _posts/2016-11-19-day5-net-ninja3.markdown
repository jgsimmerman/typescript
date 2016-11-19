---
layout: post
title: "Day 5: CSS for Beginners, by Net Ninja (Part 3)" 
date: 2016-11-19
categories: CSS
---

**Video 27: Font Size**  
- Two ways: Absolute (px); Relative (em, %)
- In the example, inheritance and overriding styles are used to demonstrate em styles 

```CSS

article{
    font-size: 16px;
}

article h2{
    font-size: 4em;
}

article p{
    font-size: 50%;
}
```
- In this example, 4em is equivalent to 16*4 or 64. em is a relative size, meaning 4x as large as the inherited style.
- 50% decreases the default font-size by 50%, making it 8px. 
- Relative measurements are ideal when working with responsive designs. 

**Video 28: Font Family**  
- Using font-stacks of similar fonts to combat cases where the user doesn't have a font installed  

```CSS

article h2, article p{
    font-family: arial, helvetica, sans-serif;
}
```

- hints at @font-face declaration and base-64 encoding later in the course, as other ways to combat uninstalled fonts.

**Video 29: Text Decoration**  
- Things like underlining links, etc. 
- You can only  have one text decoration per element. 
- Three main text decorations are: line-through; overline; and underline. You can also use none or inherit. 

**Video 30: Font Weight**  
- Changing font-weight to lighter, bolder, etc only works if the font has those settings. 
- In addition to lighter, normal, inherit, bold, and bolder, you can also use the numbers 100, 200, 300, ..., 900. Typically 100-300 is in the lighter range, 400-600 is the normal range, and 700-900 is in the bolder range. Fonts will usually not have more than three numbers, one in each  range.  

```CSS 

h1{
    font-weight: bold;
}

p{
    font-weight: 100;
    font-family: "Yu Gothic";
}
``` 

**Video 31: Text Transform**  
- Change the letter casing (hello => Hello)
- Options are: capitalize, full-width, inherit, lowercase, none, uppercase.  

```HTML

 <body>
       <p class="welcome">Welcome!</p>
        <div id="header">
            <h1>Selectors</h1>
            <h2>In CSS</h2>
            <p>Welcome to the website!</p>
        </div>

        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>
        <p>Hello there ninjas!</p>

    </body>
```  
```CSS

#header p{
    text-transform: capitalize;
}

body{
    text-transform: uppercase;
}

body > p{
    text-transform: lowercase;
}
```

**Video 32: Text Color**  
- Two types of color property: text/foreground color; background color.   

```CSS  

#header h1{
    color: chocolate;
}

#header h2{
    color: #567398;
}

#header{
    background-color: antiquewhite;
    /*background: antiquewhite;
     *
     * would also work, but with background:
     * you can pass other values besides color
     * 
     * background: url(img.jpg);
     */
}
```

**Video 33: Styling Links**  
- Not much to this video. Basic transformations applied to links.

```CSS

a{
    color: crimson;
    text-decoration: none;
    font-weight: bold;
    
}

/* hover psuedo-class */
a:hover{
    color: darkmagenta;
    text-decoration: underline;
    background-color: aquamarine;
}
```

**Video 34: Letter Spacing and Line Height**  
- Letter spacing: spacing between letters.
- Word spacing: spacing between words.
- Line height: vertical height between lines in a paragraph (similar different rules in a notebook)  

- letter-spacing: can use ems/% or px.
- line-height: tricky, because the if the vertical height of the letters is set to 12px, then it fills up an entire 12px line-height. We're specifying the height of the whole line, not the height of the space between the lines. For doublespacing, you need 24 pixels.

```CSS

p{
    font-size: 12px;
    /*letter-spacing: 2px;*/
    /*word-spacing: 2px;*/
    /*line-height: 120px;*/
    /*letter-spacing: 2em;*/ /*This inherits the 12px font-size, so 2em is the equivalent of 24px*/
    word-spacing: 0.2em;
    letter-spacing: 0.1em;
    line-height: 2em;
}
```

**Video 35: Paragraph Spacing**  
- To set paragraph spacing, we use a property called margin (this is part of the Box Model).   

```CSS

p{
    font-size 14px;
    line-height 2em;
    margin-bottom: 32px;
}
```
- This essentially wraps up the sections on fonts, texts, and letter spacing; and it provides a segue into the Box Model. 

**Video 36: The Box Model**  
- Find standard image 
- element takes up certain dimensions
- padding is an internal spacing 
- border is outside of padding
- margin controls the space between elements on a page. 

- You can use Chrome Dev Tools to visually inspect the box. 

- When you specify "width: 100%" then it can cause an overflow, because it takes up 100% of the element, plus it has padding, border, and margin.

```CSS

.box{
    margin: 30px;
    padding: 30px;
    border: 1px solid #000;
    width: 100%;
}
```
- If we specify a width of 200px, then we still have to add the margin, padding, and border; so the overall width is 322= 200 +30 + 30 + 30 +30 +1 + 1

**Video 37: Margins**

```CSS

margin: 30px 15px;
```
- This will set the top and bottom margin to 30px and the right and left to 15px. 

- Margin Collapse: When you have two elements stacked on top of eachother and they both have a margin associated with them, they combine when they meet eachother, rather than stacking.You can observe this in Dev Tools. 
- margin auto: 30px auto; will center the box within it's parent element.
- You can also use percentages to center everything, and it will also work for responsive design.

```CSS

.box{
    margin: 30px 25%;
    border: 1px solid #000;
    width: 50%; 
}
```
In this case, the box is centered because the width is set to 50% and the margin is set to 25%.

**Video 38: Padding**
- Internal spacing property within the confines of the element itself. Like othe boxes, it can be inspected in Dev tools.

```CSS

.box{
    margin: 30px;
    padding: 30px 20px 10px 5px;
    border: 1px solid #000;

}
```

**Video 39: Padding and Margin Long-hand**  
- Specify one particular side to apply margin or padding to.

```CSS 

.box{
    margin-top: 30px;
    border-left: 5px solid #000;
    padding: 20px;
}

.small{
    padding-left: 5px;
}
```

This example will display a border on the left of the element, and if you have a div with a class="box small" then you can have a smaller box with a padding of 5px instead of the larger .box padding of 20px.



