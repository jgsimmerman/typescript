---
layout: post
title: "Day 2: CSS for Beginners, by Net Ninja (Part 1)" 
date: 2016-11-16
categories: CSS
---

Today I began working through the Net Ninja ["CSS for Beginners"](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gQeDH6xYhmO-db2mhoTSrT) course on youtube. So far I've completed the first 13 modules, and I've taken these notes while coding along with the video series:

**VIDEO 4: Basic CSS Syntax**   
 
- Two components: selector and declaration  

- Selectors can target tag names, ID's, classes, etc  

- Declaration contains properties (font-size) and values (10px).  


**VIDEO 5: Inline and Embedded Styles**  

1. Inline Styling   
    - Time Consuming  
    - Tricky to manage and update  
    - Messy  
    - Good for specialized rules
2. Embedded Styling  
    - Time consuming to apply global styles  
    - Hard to maintain and update  
    - Good for making specific page styles  


**VIDEO 9: Targetting Classes and ID's**    
  
- Both used to decribe content and provide semantics  
- Classes can be used multiple times on a page  
- ID's can be used only once per page.  

- CSS works from top to bottom, so the #id below the first rule will override the h2 rule  

**VIDEO 10: The Cascade and CSS Conflicts**  
      
 - You can intentionally create conflicts by using inline and embedded styles.  
 - The bottom-most selector in the HTML file will win.  

**VIDEO 11: Inheritance**  
      
 - Child elements inherit attributes from the parent element  
 - Default styles have to be overruled.   
 `<a>` tags default to the browser default color: blue, and text-decoration: underline;  

**VIDEO 12: Selector Specificity**  
 - The most specific rule wins, so #main-content p {} won't get overruled by p{}
 
- Selector Points:

    *ID's: 100
    *Classes: 10
    *Elements: 1

- In the HTML:
{% highlight HTML %}

 <div id=main-content">
       <p>Hello there <strong> ninjas!</strong></p>
 </div>
{% endhighlight %}

- with the CSS:
{% highlight CSS %}

#main-content p{
      color: red;
}

strong{
      color: green;
 }
{% endhighlight %}

- The letters in the strong tag will be green, because the strong tag isn't inheriting the properties of the id main-content, but rather from the p element, which only has one point. Very cool!    
        
**VIDEO 13: The IMPORTANT Declaration**    
- Important Declaration prevents a rule from being overridden.    
{% highlight CSS %}
   p{ 
       color: red !important;
   }  
{% endhighlight %}

- This will ensure that p elements are always red.  

- This is a bad habit


