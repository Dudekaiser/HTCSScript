## 3. CSS and background decoration
### 1) Specifying background color and background range  
#### (1) background-color    
* syntax: __```background-color: value;```__   

__ex>__ black background 
```
<style>
  body { background-color: black; } 
</style>
```
<br>

#### (2) Control the coverage area of the background color : background-clip property   
* syntax: __```background-clip: value;```__   

| type | description |
| -------- | -------- |
| border-box | Specify background color up to border, default |
| padding-box | Specify background color including padding and excluding borders |
| content-box | Specify background color only for content area |

__ex>__   
```
  <style>
    .desc {
      border:5px dotted black;
      background-color:blue;
      width:350px;
      padding:20px;
      margin-right:20px;
      float:left;
    }
    #clip-border {
      background-clip: border-box;
    }
    #clip-padding {
      background-clip: padding-box;
    }
    #clip-content {
      background-clip: content-box;
    }
  </style>
```
<br>
<hr>

### 2) Specify a background image   
#### (1) background-image property for setting a background image   
* syntax : __```background-image: url('path for image file');```__   
* Repeatedly filling the entire web screen   

__ex>__   
```
<style>
  body {
    background-image :url('images/img.jpg');
  }
</style>
```
<br>

#### (2) Method How to repeat background image  
* syntax : __```background-repeat: value;```__   

| type | description |
| -------- | -------- |
| repeat | Repeat to fill entire screen, default |
| repeat-x | repeat horizontally |
| repeat-y | Repeat vertically |
| no-repeat | Show only once, not repeated |
<br>

#### (3) Adjust the position of the background image
* syntax : __```background-position: <Horizontal position> <Vertical position>;```__   

__ex>__   
```
<style>
  li {
    background-image:url('images/img1.png');  /* background img file */
    background-repeat:no-repeat; 
    background-position:left center;  /* positioning background img */
    padding-left:50px;  /* give space to the left (box model) */
    line-height:40px;  /* Space between lines */
  }
</style>
```
<br>

#### (4) Fix the position of the background image
* syntax: __```background-attachment: value;```__   

| type | description |
| -------- | -------- |
| scroll | When the scrollbar moved, the background image also disappears depending on the scroll position. Default value |
| fixed | Fixed position even when scrolling down |
<br>

#### ◆ Apply : Use the background property all at once  
__ex>__: Use separately   
```
body {
    background-image: url('images/img1.png');
    background-repeat: no-repeat;               
    background-position: center bottom;         /* Place below center of image */
    background-attachment: fixed;               /* fix the image */
}
```

__ex>__: Use properties all at once  
```background: url('image/img1.png') no-repeat center bottom fixed;```   

<br>

#### (5) Adjust background image size : background-size   
* syntax: __```background-size: value;```__   

| type | description |
| -------- | -------- |
| auto | Original image size, default |
| contain | Set the background image to fit inside the element |
| cover | Set the background image to fill the entire element |
| size | Horizontal and vertical values can be specified in px (pixels), “if only one value is specified = horizontal” |
| % | Set the background image based on the element it contains |
<br>

__ex>__: From top left   
① auto, ② width 200px, ③ width 50%, ④ width height 100%, ⑤ contain, ⑥ cover   
```
  #bg1 { background-size:auto;}       /* Display at original background image size */
  #bg2 { background-size:200px;}      /* Width is 200px, height is automatically calculated */
  #bg3 { background-size:50%;}        /* Background image width is 50% of element width, height is automatically calculated */
  #bg4 { background-size:100% 100%;}  /* Background image width and height are 100% of the element width and 100% of the element height */ 
  #bg5 { background-size:contain;}    /* Display the background image fully visible inside the element */
  #bg6 { background-size:cover;}      /* Display background image to completely cover element */
```
<br>
<br>
<hr>

### 3) gradient effect      
### (1) 선형 그라데이션   
* syntax : __```linear-gradient(to <Arrival direction or angle>, <Color 1 Color 2>);```__   
* Gradients that appear horizontally, vertically, and diagonally   
<br>

__ex1>__   
```
.grad {
    background: blue;
    background: linear-gradient(to right bottom, blue, white);      /* From top left to bottom right, blue to white */
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181079783-0ef46397-654a-4aba-a28f-44e58e226188.JPG width=400 alt="box model"></a>   

<br>

__ex2>__: Linear gradient (angle)  
* 90 degrees, 180 degrees, 270 degrees clockwise(0 degrees at the top)  
```
.grad { 
  background: #fff;                                    
  background: linear-gradient(45deg, #f00, #fff);      /* 45 degrees (top right), from red to white */
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181080636-7e04a798-6e79-4837-804a-f2864be587f0.JPG width=400 alt="box model"></a>   

<br>

__◇ color stop point(color-stop)__: Colors that change in gradient → Expression of two or more colors  
__ex>__   
```
.grad {
    background: #06f; 
    background: linear-gradient(to bottom, #06f, white 30%, #06f);    /* Specify a color stop at 30% from the top */
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181083661-d12bdb78-d7b0-47a2-8407-f3458838588b.JPG width=400 alt="box model"></a> 

<br>
<hr>

### (2) circular gradient  
* syntax: __```radial-gradient(<shape> <size> at <position>, <color stoppoint>);```__   
* Gradient that appears in concentric circles starting from the center of the circle   
   * default : ellipse
<br>

__ex>__   
```
/* Gradient that changes from white to yellow to red in an oval shape */
.grad1{
    background:radial-gradient(white, yellow, red);
}


/* circular gradient */
/* Gradient that changes from white to yellow to red in a circular position (20% above 20% left) */
.grad2{
    background:radial-gradient(circle at 20% 20% white, yellow, red);
}
```
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181090401-258693e1-5f4d-429f-a05c-023cbbcbdbe8.JPG width=600 alt="box model"></a> 
<br>
<br>

#### (2-1) Size value   
| type | description |
| --- | --- |
| closest-side | until it reaches the side closest to the center of the gradient |
| closest-corner | Until it reaches the vertex closest to the gradient center |
| farthest-side | until it reaches the side furthest from the center of the gradient |
| farthest-corner | Until it reaches the vertex furthest from the gradient center |
<br>

__ex>__   
① Nearest side, ② Nearest vertex, ③ Farthest side, ④ Farthest vertex   
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181091692-e98d9ef8-b5d0-44f9-8aa4-c6b621ee286c.JPG width=80% alt="box model"></a> 
<br>
```
#div1{
    background:darkgreen;
    background:radial-gradient(circle closest-side at 30% 40%, white, yellow, green);
}

#div2{
    background:darkgreen;
    background:radial-gradient(circle closest-corner at 30% 40%, white, yellow, green);
}

#div3{
    background:darkgreen;
    background:radial-gradient(circle farthest-side at 30% 40%, white, yellow, green);
}

#div4{
    background:darkgreen;
    background:radial-gradient(circle farthest-corner at 30% 40%, white, yellow, green);
}
```
<br>
<br>

#### (2-2) location   
* __```at location```__   
* __location value__: left, right, top, bottom, center, percentage(%)
   * If the position is omitted, it is recognized as ```center``` 

__ex>__   
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181094479-4d350658-eaf3-42fe-8d9e-79b01107ea8c.JPG width=15% alt="box model"></a> 
```
/* A circular gradient starting at 20% and going from white to blue. */
.grad {
    background: blue;  
    background: radial-gradient(circle at 20% 20%,white,blue);    
}
```
<br>
<br>


#### (2-3) gradient pattern   
* linear gradient pattern: __```repeating-linear-gradient()```__   
* circular gradient pattern: __```repeating-radial-gradient()```__   
<br>

__ex1>__: Gradient pattern with unclear ends  
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181098809-8383f8a3-ba46-4f09-871d-17174898e7c0.JPG width=60% alt="box model"></a> 
```
.grad1 {
    background: red;
    background: repeating-linear-gradient(yellow, red 20px); 
}

.grad2 {
    background: #ccc;
    background: repeating-radial-gradient(circle, white, #ccc 10%); 
}
```
<br>
<br>

__ex2>__: Gradient pattern with clear edges 
  
<a href="#"><img src=https://user-images.githubusercontent.com/108077414/181099664-80366660-0673-495d-a7c6-0cdaceaa4a2c.JPG width=60% alt="box model"></a> 
```
.grad1 {
    background: red;
    background: repeating-linear-gradient(yellow, yellow 20px, red 20px, red 40px);
}

.grad2 {
    background: #ccc;
    background: repeating-radial-gradient(circle, white, white 10%, #ccc 10%, #ccc 20%);
}
```
