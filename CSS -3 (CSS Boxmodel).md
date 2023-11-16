## 2. CSS and box model   
### 1) Block-level elements vs. inline-level elements 
#### ① Block-level elements   
* Tag that occupies an entire line  

__ex>__   
```<div> a <p class="accent"> b </p> c </div>```   
<br>

#### ② Inline-level elements   
* Tag that occupies only some part of a line   
* The line may contain other elements 

__ex>__   
```<div> a <span class="accent"> b </span> c </div>```   
<br>
<br>
<hr>

### 2) Box model   
* Content area < padding < box border < margin   

__① Content area__: The part where the content located in 
__② padding__: Space between content area and box   
__③ border__: Border thickness or Box  
__④ margin__: Space between box models   

<a href="#"><img src=https://user-images.githubusercontent.com/108077414/180662223-7223a23e-9c1b-47d5-a5d6-6bd97e1636cb.png width="400px" alt="box model"></a>
<br>
<br>

### (1) Contents aread   
#### ◆ ① width and height specify the size of the content area   
| type | description |
| -------- | -------- |
| size | Specified by px or em value |
| % | Specify percentage (%) based on parent element |
| auto | Automatically set, default |

__ex>__   
```
  .box1 {
    width: 200px;
    height: 100px;
    padding: 20px;
    border: 10px solid black;  
  }
```
<br>

#### ◆ ② Box-sizing to calculate the size of a box model  
* syntax : __```box-sizing: value ;```__   

| type | description |
| -------- | -------- |
| border-box | Specify the total width value including border and padding |
| content-box | Specify content width value, default value |

__ex>__   
```
  .box1 {
    box-sizing: border-box;
    width: 200px;            
    height: 100px;
    padding: 20px;
    border: 10px solid black;
  }
```
<br>

#### ◆ ③ box model shadow effect : box-shadow   
* 기본 태그: __```box-shadow: <Horizontal distance> <Vertical distance> <degree of cloudiness> <Degree of smearing> <Color> inset;```__   

| type | description |
| -------- | -------- |
| Horizontal distance | How far away the shadow is horizontally / 'positive number (+) = right' |
| Vertical distance | How far away the shadow is vertically / 'positive number (+) = down' |
| degree of cloudiness | If omitted, 0 is the default dark shadow / negative X, the larger the value, the softer the shadow. |
| Degree of smearing | Default is O, the larger the value, the more spread out the shadows are. |
| Color | Default is black, 1 color or multiple colors can be specified by separating them with spaces. |
| inset | Create inner shadow |

__ex>__   
```
  .box1 { box-shadow: 2px -2px 5px 0px; }  → cloudiness
  .box2 { box-shadow: 5px 5px 15px 5px blue; }  → cloudiness, smearing, color
```

<br>
<hr>

### (2) Border   
#### ◆ Box model value specification direction   
* __clockwise__: top → right → bottom → left   
<br>

#### ◆ ① Border style ```border-style```   
* syntax : __```border-style: value;```__   

| type | description |
| -------- | -------- |
| none |  |
| hidden | There are no borders |
| solid | solid border |
| dotted | dotted border |
| dashed | Short straight border (like a dotted line) |
| double | Double line border, border-width value = space between two lines |
| groove | The window appears as if it were carved, with a three-dimensional border that feels like a groove. |
| inset | border-collapse: In case of separate, it is displayed as if it is embedded in the ground, and in case of collapse, it is displayed the same as the groove. |
| outset | border-collapse: In case of seperate, it is displayed as if it is protruding from the window, and in case of collapse, it is displayed just like a ridge. |
| ridge | Appears as if sticking out of window |
<br>

#### ◆ ② border thickness ```border-width```   
* syntax : __```border-width: value ;```__   

| type | description |
| -------- | -------- |
| thin, medium, thick | Specify border thickness |
| px(pixel) | Specify thickness by pixel value |

__ex>__   
```
<style>
#box1 { border-width: 2px; }   → all directions
#box2 { border-width: thick thin; }   → thick (top, bottom) / thin (left and right)
#box3 { border-width: thick thin 2px; }   → thick (top) / thin (Right - also applied to left) / 2px (bottom)
</style>
```
<br>

#### ◆ ③ Border color ```border-color```   
* syntax : __```border-color: value;```__   
* color name , hexadecimal, RGB, etc.

__ex>__: Used all at once within the border  
```
p {
  padding: 10px;
  border: 3px dotted blue;
}
```
<br>

#### ◆ ④ round border ```border-radius```   
* syntax : __```border-radius: value;```__   

| type | description |
| -------- | -------- |
| size | Set radius size in px, em units |
| % | Set percentage (%) based on the size of the current element (horizontal/vertical width) |
<br>

#### ◇ round border of image   
```
<head>
  <style>
    .circle { border-radius: 50% }
  </style>
</head>
<body>
  <img class="circle" src="images/photo.jpg">
</body>
```

#### ◇ Make it round only for certain vertex   
* syntax: __```border-specific location-radius: value;```__   
* ellipse vertex : __```border-specific location-radius: <horizontal radius> <vertical radius> ;```__   

__ex1>__   
```
#round1 {
  border: 2px solid blue;
  border-top-left-radius: 20px;    → make left top round
  border-top-right-radius: 20px;   → make right top round
}
```

__ex2>__   
```
.round2 {
  border-bottom-right-radius : 50% 30%;   → Round the lower right corner to 50% width and 30% height.
}
```

<br>
<hr>

### (3) Space properties  
#### ◆ ① margin    
* syntax : __```margin: value;```__   
* specific direction : __```margin-specific position: value;```__

| type | description | example |
| -------- | -------- | -------- |
| size | Width and height → set in px, em units | margin: 50px; |
| % | Set percentage (%) based on parent element | margin: 0.1%; |
| auto | Automatically assigned to the value specified in the display property |  |
<br>

#### ◇ margin superposition   
* When placing elements vertically, when the margin and margin meet, they overlap with the larger value.
   * 50px + 30 px = 50px   

__ex>__:    
```
   div {
      width: 200px;
      height: 100px;
      margin: 30px;      → Margin settings
    }
    #box1 { background: rgb(0, 77, 243); }
    #box2 { background: rgb(255, 72, 0); }
    #box3 { background: rgb(18, 219, 0); }
    
  <div id="box1"></div>   → The 30px bottom margin of box1 and the 30px top margin of box2 overlap, resulting in a total of 30px instead of 60px.
  <div id="box2"></div>
  <div id="box3"></div>
```
<br>

#### ◆ ② padding property   
* Set padding so that the border and content do not stick together.  

<br>

__ex>__:    
```
<style>
 table {
   caption-side: bottom;
   border: 1px solid black;
   border-collapse: collapse;
 }
 td, th {
   border: 1px solid #222;
   padding: 10px;           
 }
</style>
```

<br>
<hr>

### (4) Layout property   
#### ◆ ① display property  
* Decide how to place them → block level elements / inline level elements  

| type | description |
| -------- | -------- |
| block | Inline level element → Block level element |
| inline | Block level element → Inline level element |
| inline-block | The overall form is inline level, but each element inside is used as a block level element. |
| none | Do not display the element on the screen |
<br>

__ex> Create horizontal navigation__  
```
<style>
  nav ul {
    list-style: none;  → remove list
  }
  nav ul li {
    display: inline-block;
    border: 1px solid black;
    padding: 20px;
    margin: 0 20px;
  }
</style>
```
<br>

#### ◆ ②-1 float property   
* Left or right placement 

| type | description |
| -------- | -------- |
| left | Place the element on the left side of the document |
| right | Place the element on the right side of the document |
| none | Place on either left or right |

__ex>__:  Place the photo on the left side of the document 
```
<head>
  <style>
    img {
      float:left;  /* float on the left */
      margin-right:40px;
    }
  </style>
</head>
<body>
  <img src="images/float.png">
</body>
```
<br>

#### ◆ ②-2 clear property
* Turn off float property  

| type | description |
| -------- | -------- |
| left | float: release left |
| right | float: turn off right |
| both | float: clear both left and right |
<br>

#### ◇ Create a 3-column layout with float  
```
#container {
  width:1200px;   /* Width of entire content */
  margin:20px auto;  /* Set the left and right margins to auto to center the content on the screen. */
}
#header{
  width:100%;  /* Same width as the parent element */
  height:120px;  /* header height */
  background-color:black;
}
#left-sidebar {
  width: 250px;   /* width of sidebar */
  height:600px;  /* Sidebar height */
  background-color:black;
  float: left;  /* floating to the left */
}
#contents {
  width: 800px;  /* width of body */
  height:600px;   /* height of text */
  background-color:black;
  float: left;  /* floating to the left */
}
#right-sidebar {
  width: 150px;   /* width of sidebar */
  height:600px;  /* Sidebar height */
  float: left;  /* floating to the left */
  background-color:black;
}
#footer {
  width:100%;  /* Same width as the parent element  */
  height:100px;  /* footer height */
  background-color:black;
  clear:left;		/* Turn off floating */
}
```

<br>
<hr>

### (5) Positioning web elements   
#### ◆ ① location properties   
| type | description |
| -------- | -------- |
| left | Specifies how far to the left |
| right | Specifies how far to the right |
| top | Specifies how far to the top |
| bottom | Specifies how far to the bottom |
<br>

#### ◆ ② position property   
| type | description |
| -------- | -------- |
| static | Place in creation order, default |
| relative | Placement & location value can be specified in order of creation | 
| absolute | Specifies the position relative to the parent element or parent element |
| fixed | Specify & fix position value → Fix at that position even if the scroll bar is lowered (used for banners, advertisements, etc) |

__ex1>__   
```
<style>
  #static { position:static; }
  #relative-1{ position:relative; }
  #relative-2 {
    position:relative;   /* positioning - relative */
    left:100px;  /* 100px away from the left */
    top:-50px;   /* -50px away from the top (moved up) */
  }
  #fixed {
    width:100px;
    height:100px
    background-color:black;
    position:fixed;  /* positioning - fixed */
    right:30px;  /* 30px away from the right */
    top:30px;  /* 30px away from the top */
  }
</style>
```
<br>

__ex>__: __```absolute```__ example   
```
#contents {
 background:url("../images/img.jpg") no-repeat;
 background-size:cover;
 width:800px;
 height:500px;
 margin:0 auto;
 position:relative;    
}
h1 { 
  color:#fff; 
  font-size:120px;
  text-shadow: 2px 3px 0 #000;      
  position:absolute;   
  right:100px;
  bottom:100px;
}
```
