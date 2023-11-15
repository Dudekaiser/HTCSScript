## 1. CSS
* CSS source
: The html and css sources are separated from each other, so we only need to modify the necessary parts.
<br>

### 1) Styles and Style Sheets
* Style : Style determines the appearance of an HTML document
* Style sheet : A collection of styles in one place(in html <style> or in file.css)
<br>

#### (1) internal style sheet: Sheets saved in the document
__◇ syntax:__   
```
<style>
  Selector {
    Property : property value;
  }
</style>
```

__ex1>__ : used in <head>
```
<style>
  h1(selector) {
    color(property): blue(property value); → style rule
    font-size: 5.5px;
    font-style: italic;
  }
</style>
```
<br>

__◇ inline style__: Styles in tags

__ex2>__ : used in <body>
```<h1 style="color: black">red flavor</h1>```   
<br>   
<br>

#### (2) external style sheet: file.css   
: Save to CSS folder with extension .css   
: Only the contents of __```<style>```__ saved (selector, style rule)   
: Write link in <head> of html document 
: The same css file can be used in multiple places, so we can remove duplicate code   

* syntax   
: __```<link href="path of css file" rel=stylesheet```__   

__ex>__   
```   <link href="css/mycss.css" rel="stylesheet">```

<br>
<hr>

### 2) Selector
#### (1) Universal Selector
: Reset existing browser styles
```
<style>
  * {
    margin:0;
    padding:0;
  }
</style>
```

<br>

#### (2) Tag selector
: When we want to apply only to specific tags

__ex>__ : only for <p> tags  
```
p {
  color: black;
}
```
<br>

#### (3-1) class selector   
: When we want to apply it only to a specific part  
: Can be used multiple times  

* syntax : __```.classname { style }```__   

__ex1>__
```
① make style in <head>
.classname {
  color: blue;
}

② apply
<p class="classname">content</p>
```
<br>

__ex2>__ : When we apply only to specific letters  
* __```<span>specific letters</span>```__   
```<p>only to specific letters <span class="classname">want to</span>apply</p>```
<br>
<br>

#### (3-2) id selector   
: When we want to apply it only to a specific part  
: Can be used multiple times   

* syntax: __```#id { style }```__   

__ex>__   
```
① make style in <head> part
#container {
  border: 10px solid black;   (border style)
  padding: 50px;   (padding between border and content)
}

② apply
<div id="container">
```
<br>
<br>

#### (4) group selector   
: A group of selectors that use the same style rules   

* syntax: __```selector1, selector2 { style }```__   

__ex>__
```
h1, p {           <!-- h1 and p want to have same style-->
  color: blue;
}
```

<br>
<hr>

### 3) Cascading Style Sheets   
__◆ Cascading Meaning__     
* To prevent style application conflicts, determine which style to apply based on priority.   
<br>

__◇ Cascading Principle__   
① Style priority: Priority is determined based on the importance and scope of application of the style rule, and styles are applied from top to bottom according to that priority.
② Style inheritance: Passing the style of the parent element to the child element (indentation) from top to bottom according to the inclusion relationship of tags.
<br>
<br>

#### (1) Principle 1: Style Priority   
① Depending on how important it is 
: __User style > Creator style > Browser style__   
> * User Style: Style created by the system (no user control)  
> * Creator Style: Style created by the creator when creating the website.  
> * Browser's style : Browser's default style
<br>

② Depending on how the scope can be limited   
: __!important > inline style > id style > class style > type style__   
> * !important: A style that takes precedence over any other style   
> * Inline styles: Styles that apply only to that tag   
> * id style: A style that applies only to specific parts (used only once in the document)  
> * Class Style: Style that applies only to a specific part (can be used multiple times) 
> * Type style: A style that applies only to a specific tag (applies to all the same tags in the document) 
<br>

③ according to source order
: If importance and specificity are the same, decision is made according to source order. 
: Styles that come later in the source overwrite styles that come earlier 
<br>
<br>

#### (2) Principle 2: Style Inheritance  
* If we do not specify a separate style for the child element, the style properties in the parent element are passed on to the child element.
    * ex> Font size: If the font size is not specified separately in the text paragraph, the font size of the body tag (parent element) is applied to the child element.
* However, not all properties of a parent element are inherited by child elements.
    * ex> Text color is inherited, but background color is not inherited.   
<br>

__ex1>__ : Overridden by later rules  
```
h1 {
  color: black;  (First)
}
p {
  color: brown;
}
h1 {
  color: green;  (second rule) → this color : green is applied
}
```

__ex2>__ : Overridden by inline style rules 
```
<head>
  <style>
    p {
      color: green;
    }
  </style>
</head>
<body>
  <h1>red scent</h1>
  <p style="color: blue;">It is called red scent because of the red blob on the peel..</p> → inline style
</body>
```

__ex3>__ : __```!important```__   
```
<head>
  <style>
    h1 {
      color: brown !important;  → HIGHEST PRIORITY
    }
  </style>
</head>
<body>
  <h1 style="color: blue;">red scent</h1>  → not blue applied
  <p>It is called red scent because of the red blob on the peel..</p>
</body>
```

__ex4>__ : style inheritance   
```
<head>
  <style>
    body {
      font-size:20px;  → Also applies to the <p> tag of the body
    }
  </style>
</head>
<body>
  <h1>red scent</h1>  → The title uses the browser's default font size.
  <p>It is called red scent because of the red blob on the peel..</p>
</body>
```


