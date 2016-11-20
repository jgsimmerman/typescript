---
layout: post
title: "Day 3: CSS for Beginners, by Net Ninja (Part 2)" 
date: 2016-11-17.
categories: CSS
---

Today I continued working through the Net Ninja ["CSS for Beginners"](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gQeDH6xYhmO-db2mhoTSrT) course on youtube. Over the weekend, I'll probably take a break to work through the CodeSchool tutorials, since they're having a free weekend. For now, I'll pick up where I left off yesterday, with lesson 14:

 **VIDEO 14: Targeting Multiple Elements** 

 - Multiple elements can be targeted by one rule such as:

{% highlight CSS %}
p, span, a, li {
    color: red;
    font-size: 14px;
    font-weight: bold;
    font-family: Arial;
}
{% endhighlight %}
**VIDEO 15: Descendant Selectors**
- In the following code, everything nexted between the <body> tag would be considered a descendant of the body tag:

{% highlight HTML %}
<body>
    ...
</body>
{% endhighlight %}  
- Descendants can be targeted by the id/class followed by the element, such as:

{% highlight CSS %}
#main-content p {
    color: red;
}
{% endhighlight %}
 - To go deeper, you could use:

{% highlight CSS %}
#main-content #sub-content p {
    color: red;
}
{% endhighlight %}
or you could simply target the #sub-content id. 
    
**VIDEO 16: Child Selectors**
    
- Child selectors are direct descents of a given tag, but further descendants aren't child selectors.
- The child combinator > is used to select direct child elements, such as:

{% highlight CSS %}
#main-content > p {
    color: red;
}
{% endhighlight %}
In this example, it target p elements that are a direct child element of main-content.

**VIDEO 17: Adjacent Selectors**

- The adjacent combinator + is used to select each element that comes directly after another specified element:

{% highlight CSS %}
#all-articles h2 + p {
    color: green;
}
{% endhighlight %}    
- In this given example, it will select it will mark the p tags adjacent to an h2 tag as green, such as in this html:  

{% highlight HTML %}
<h2>Article #1</h2>
<p>This will be green</p>
<p>This will NOT be green</p>

<h2>Article #2</h2>
<p>This will be green</p>
<p>This will NOT be green</p>
{% endhighlight %}
**VIDEO 18: Attribute Selectors**

- The attribute selector syntax follows the format element[attribute]{} such as span[class]{}
- You can become more specific by doing something like:

{% highlight CSS %}
a[title="Search Engine"] {
    color: red;
}
{% endhighlight %}
    - This will target links where title="Search Engine"
- Pattern Matching: If you want to target all elements of a specific class without excluding elements that contain other classes, you can put a tilde in fron the of the = sign.

{% highlight CSS %}
span[class~="deck"] {
    color: purple;
}
{% endhighlight %}

    - will target all of the spans of class deck, including the one with class halls:

{% highlight HTML %}
<span class="deck halls">Yo, I'm a span tag too</span>
<span class="deck">This is a deck of spans</spans>
<span class="deck">I like the span decks</span>
{% endhighlight %}

- Similarly, if you want to target specific file types, you can place a $ before the = sign, as in:

{% highlight CSS %}
a[href$="pdf"] {
    color: green;
}
{% endhighlight %}
This will target all of the a links with an href that ends in pdf.
- Another possibility is to single out links that start with something using the ^ symbol, such as:

{% highlight CSS %}
a[href^="http"] {
    color: pink;
}
{% endhighlight %}
- This is really cool stuff and I'm excited about this. I fuond a couple of CSS-Tricks articles on this topic that I'll have to go back and study further. [The Skinny on CSS Attribute Selectors](https://css-tricks.com/attribute-selectors/) which was published in 2010, and also 2012's [\[attribute\]](https://css-tricks.com/almanac/selectors/a/attribute/).

**Video 19: Pseudo-Classes**

- Special keywords that go after selectors and can be used to target things we couldn't normally select, such as:  
    
    1. Special behavioral states
    2. Advanced structural elements

- Dynamic: Based on behaviors, such as hover effects, button clicks, checking radio boxes, etc.  
- Structural: e.g. Parent-Child relationships, the 5th <li> tag in a list, a parent tag with no children, etc.

- The syntax layout for Pseudo-Classes is: selector:keyword { declaration }

{% highlight CSS %}
a:hover {
    color:red;
}

#main-content:hover {
    background: gray;
}
{% endhighlight %}

**Video 20: Hover, Visited and Activve Psuedo Classes**  

- Dynamic Pseudo Classes

{% highlight CSS %}
a:hover {
    color: red;
}

a:active {
    color: green;    
}

a:visited {
    color: purple;
}
{% endhighlight %}

**Video 21: First and Last Child Pseudo Classes**  

- Structural Pseudo Classes
- Can target the first and last chil directly

{% highlight CSS %}
article p:first-child {
    font-weight: bold;
}

article p:last-child {
    color: red;
}
{% endhighlight %}

**Video 22: First and Last of-Type Pseudo Classes**  

- Similar to first and last child, but targets a specific type of selector.

{% highlight CSS %}
article p:first-of-type {
    font-weight: bold;    
}

article p:last-of-type {
    color: red;
}

{% endhighlight %}

**Video 23: N-th Child Pseudo Classes** 

- Allows the selection of specific child elements. Arguments can be passed  

{% highlight CSS %}
li:nth-child(1), li:nth-child(7) {
    font-weight: bold;
}
{% endhighlight %} 
will make the 1st and 7th elements bold, given a list  

{% highlight HTML %}
      <li>Item List</li>
      <li>item01</li>
      <li>item02</li>
      <li>item03</li>
      <li>item04</li>
      <li>item05</li>
      <li>Half Way TITLE</li>
      <li>item06</li>
      <li>item07</li>
      <li>item08</li>
      <li>item09</li>
      <li>item10</li>
{% endhighlight %}

- You can also pass in keywords as Arguments

{% highlight CSS %}
li:nth-child(even){
    background: grey;
}

li:nth-child(odd) {
    background: pink;
}
{% endhighlight %}

- Or formulas  

{% highlight CSS %}
li:nth-child(3n + 1) {
    color: green;
}
{% endhighlight %}

- Okay, this is pretty cool stuff. 

**Video 24: Nth of Type Pseudo Classes**  

- You can also use the nth-of-type selector to select a particular number of a certain type of element, so you can select the first article using:  

{% highlight CSS %}
article:nth-of-type(1) {
    background: grey;
}
{% endhighlight %}  
- Formulas and keywords can be used in the same way as with the nth-child selector.  

**Video 25: Combining Selectos**    

- You can combine selectors, such as element and class selectors

{% highlight CSS %}  
article.featured-content {
    background: red;
}

div.featured-content {
    background: blue;
}
{% endhighlight %}

**Video 26: The Universal Selector** 
- Allows you to style every element or tag within one rule using the star operator. A basic syntax example is:

{% highlight CSS %}
*{
    color: blue;
}
{% endhighlight %}

- Using the body selector doesn't override default browser styling, but the universal selector does.
- Generally should be avoided, but useful for CSS resets. 

This is roughly the half-way point of the Net Ninja series and it also concludes the section on selectors before moving into fonts and text. I'll probably take a break to check out the CodeSchool offerings before coming back to Net Ninja, but so far this is a great video tutorial. I'm also practicing adding each of these techniques to the CSS Zen Garden template as I go along, to solidify what I'm learning. Right now I'm not getting into styling my Zen Garden; I'm just changing things around using the techniques that are being covered. So far, that seems to be helpful. 




