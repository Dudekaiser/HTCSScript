## 7. Media query
* We can apply the style we need by specifying more specific conditions. Media query helps this.
<br>

* Media query can be used in following situations.
<br>
① When we apply styles based on specific conditions using CSS @media and @import @rules.
<br>
② To point to specific media using the media property on <style>, <link>, <source> (en-US), and other HTML elements.

### 1) method how to apply media query

#### (1) <link>
 * ```<link>``` tag is located in ```<head>``` tag, so CSS file is loaded, when the conditions in the media property is satisfied.

 ```html
<link href="cssfilename.css" media ="screen and (min-width : 512 px) and (max-width : 1024 px)">
 ```
<br>

#### (2) <style>
 * ```<style>``` tag is located in ```<head>``` tag and style is applied, when the conditions in the media property is satisfied.

 ```html
<style type = "folder/css" media = "screen and (min-width : 512px) and (max-width : 1024 px)">
/*style*/
</style>
```
<br>

#### (3) <style>-@import
 * Use @import within the <style> tag to load the CSS file when the media query in the latter part is satisfied.

```html
<style>
  @import url(cssfile.css) screen and (min-width : 152px) and (max-width : 1024px);
</style>
```
<br>

#### (4) CSS file
 * Write a media query directly in the imported CSS file or within the <style> tag and apply the style when satisfied.

```html
@media screen and (min-width : 512px) and (max-width : 1024px)
```
<br>

### 2) Mediaquery syntax :
 ```@media only|not screen and (property:value) { ... }```

 * The only or not keyword is literally placed in the position of only|not.
 * The only keyword refers to only the conditions that located behind.
 * And the not keyword refers to conditions excluding the conditions that located behind.
 * Screen is media type.
 * We can list multiple media types using commas.

 | Media type | descryption |
 | ---- | ---------- |
 | all | All media types |
 | aural | voice synthesizer |
 | braille | braille display device |
 | handheld | A small screen that can be viewed while being held in hand |
 | print | For print |
 | projection | projector |
 | screen | computer screen |
 | tty | Media using fixed characters, such as telex, terminals or manual transfer devices with limited display capabilities |
 | tv | A device that outputs audio and video simultaneously |
 | embrossed | Braille marking device printed on the page |

<br>
 
 | Property | Value |
 | ---- | ---------- |
 | width | the width of a web page |
 | height | the height of a web page |
 | device-width | Actual width length of the device |
 | device-height | Actual height length of the device |
 | orientation | Measure the width and height and determine it as landscape if the width is longer, and as portrait if the height is longer |
 | aspect-ratio | Determine the ratio of width and height |
 | device-aspect-ratio | device's screen ratio |
 | color-index | Maximum number of colors used by the device |
 | monochrom | Determine the level between white and black on devices that use only black and white colors |
 | resolution | Determine the supported resolution. dip or dpcm |
 | color | Determine the maximum number of color bits used by the device |

 * Media query properties do not use operators such as = > <
 * Instead, add min- or max- in front of the property name to determine the minimum and maximum values
 * It can be listed as and (property 1: value) and (property 2: value) and can also be set as a range when we use min- and max-

__ex>__
* When the device accessing the web is a screen, the background color is blue if the width is less than 100px (max-width: 100px), green if it is 200px or more, and red if the value is in between values.

```html
<style>
 div{
   width : 100%;
   height : 100%;
    }
    @media screen and (max-width : 100px) {
       div{background-color : blue;}
    }
    @media screen and (min-width : 100px) and (max-width : 200px) {
       div{background-color : red;}
    }
    @media screen and (min-width : 200px) {
       div{background-color : green;}
    }
</style>
```
<br>

### 3) Grid
 * A grid divides the width of a web screen into several columns.
 * Keep the width of the columns and the spacing from other columns constant.

#### (1) Fluid Grid
 * Fluid grid sets the width of the grid to an em or % value rather than a fixed value.
 * This is a method of changing the size of the column relatively according to the change in horizontal width.


__ex>__
* This is an example in which the width of the div changes depending on the width of the web while the layout is maintained.
* By giving the div's width value as % value rather than a fixed value, the div's width value changes dynamically according to the total width. 


```html
 <style>
  div{
    height : 100%;
    float : left;
     }
  #grid_1{
    width : 30%;
    background-color : green;
     }
  #grid_2{
    margin-left : 5%;
    width : 45%;
    background-color : blue;
     }
  #grid_3{
    margin-left : 5%;
    width : 15%;
    background-color : red;
     }
 </style>

<body>
  <div id = "grid_1"></div>
  <div id = "grid_2"></div>
  <div id = "grid_3"></div>
</body>
```
<br>

