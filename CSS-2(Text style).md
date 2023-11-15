## 1. CSS   
### 4) Style of expressing text  
### (1) font style   
| type | description |
| -------- | -------- |
| font-family | Specify font type |
| font-size | Specify font size |
| font-style | Specifies whether to display text in italics |
| font-weight | Specify font thickness |
<br>

① __font-family__   
* syntax : __```font-family: font type```__   

__ex1>__
```
<style>
  h1 {
    font-family: fantasy;
  }
</style>
```

* Set up 2 or more fonts: __```font_family: font type, font type```__   
   * If there is no font type in front, the behind font type is applied.
<br>

__ex2>__   
```body { font-family: monospace, cursive, fantasy }```   
<br>
<hr>

② __font-size__   
* syntax: __```font-size: font size as we want```__   

| unit | description |
| -------- | -------- |
| px | 1 px |
| pt | 1 point |
| em | Width of the letter M (width) = 1em = 16px |

__ex>__ : ```font-size: 10px```   
<br>
<br>

③ __font-style__   
* syntax : __```font-style: name of font style```__   

| font property | description |
| -------- | -------- |
| normal | default value |
| italic | Italics, mainly used |
| oblique | Italics |

__ex>__ : ```font-style: italic```   
<br>
<br>

④ __font-weight__   
* syntax : __```font-weight: font size```__   
* Expressed in thickness between 100 and 900
* 400 is the default thickness, anything less than 400 is thin and thick, and around 700 is moderately thick.

| type | description |
| -------- | -------- |
| normal | normal thickness, 400 |
| bold | Think , 700 |
| bolder | thicker than the original |
| lighter | thinner than the original |
| numeric value | Thickness value between 100 and 900 |

__ex>__: ```font-weight: 400```   

<br>
<hr>

### (2) Web font   
* The more web fonts you use, the slower your website may load.

#### ① syntax :   
```
@font-face {
  font-family: font name;
  src: font file;
}
```

__② google font__ - select language - select font - select this style - ```<link>``` or @import   
   * Copy @import link - ```<style>``` Paste it direct after the style tag.  
   * Copy/paste the font-family part as well. 

__ex>__   
```
<head>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nanum+Brush+Script&display=swap');
    
    h1 {
      font-family: 'Nanum Brush Script', serif;   → Alternative fonts as web fonts may not apply
  </style>
</head>
<body>
  <h1>red scent</h1>
  <p>peels has red color...</p>
</body>
```

<br>
<hr>

### (3-1) Web color   
#### ① color property   
* syntax : __```color: color what we want;```__   
<br>

#### ② Hexadecimal notation   
* #6 digits  
* The two digits from the beginning are grouped together and expressed as the quantities of red (R), green (G), and blue (B).
* If nothing is mixed, it is displayed as 00, if it is completely mixed, it is displayed as ff. 
   * 000000 (black) to ffffff (white)
* If two digits are duplicated, they can be abbreviated   
   * #ffff00 → #ff0,  #cccccc → #ccc   
<br>

#### ③ hsl / hsla notation   
* 3 digit number
* Expressed as a quantity of color(hue), saturation, brightness(light)
* Transparency can be adjusted with the alpha (a) value at the end
   * hsla(240, 100%, 500% 0.3)
   * Values from 0 to 1: 1 is opaque, 0 is completely transparent
<br>

#### ④ rgb / rgba notation
* 3 digit number
* Expressed in quantities of red (R), green (G), and blue (B)
* Transparency can be adjusted with the alpha (a) value at the end
   * color.rgba(255,0,0,0.3)
   * Values from 0 to 1: 1 is opaque, 0 is completely transparent
<br>


__ex1>__   
```
<head>
  <style>
    h1 {
      font-size:120px;
      color: orange;
    }
  </style>
</head>
<body>
  <h1>red scent</h1>
</body>
```
<br>
<hr>

### (3-2) Text color  
#### ◆ Text style properties   
| Type | Description |
| -------- | -------- |
| color | font color |
| text-decoration | Underline or strikethrough |
| text-transform | Capital letters (entire text or first letter) |
| text-shadow | shadow effect |
| letter-spacing | letter spacing |
| word-spacing | space between words |
| text-align | How to align text |
| line-height | Adjust line spacing |
<br>

#### ① text-align : Arrange Text   
* syntax : __```text-align: property value ;```__   
#### ◇ text-align property value
| type | description |
| -------- | -------- |
| start | Align to start of current text line |
| end | Align to the end of the current line of text |
| left | Left align |
| right | Right align|
| center | center align |
| justify | align both sides |
| match-parent | Align paragraphs according to parent element |

__ex>__   
```
① <head> part
  <style>
    .tstyle {
      text-align: center;
    }
  </style>

②  apply in <body>
  <p class="tstyle">content</p>
```
<br>

#### ② line-height : Adjust line spacing
* syntax : __```line-height: numeric value ;```__   
   * Number (multiple, 2.0), pixel (px), percentage (%)

__ex>__   
```
① <head> part
  .tstyle {               <!--class name is "tstyle">
    line-height: 30px;
  }
```
<br>

#### ③ text-decoration : Underline or strikethrough
* syntax : __```text-decoration: property value;```__   

#### ◇ text-decoration property value
| type | description |
| -------- | -------- |
| underline | __ |
| overline | top line |
| line-through | strikethrough |
| none | When we delete the underline of a URL link |

__ex1>__   
```
① <head> part
  .tstyle-2 {
    text-decoration: underline;
  }
  
② apply in <body>
  <p>content<span class="tstyle-2">content</span></p>
```
<br>

__ex2>__: __```none```__: Mainly used to erase the underline of text links
```
① <head> part
  .a {
    text-decoration: none;
  }

② apply in <body>
  <p><a href="link address">content</a></p>
```
<br>

#### ④ text-shadow : add shadow
* syntax: __```text-shadow: <Horizontal distance> <Vertical distance> <Smearing degree> <Color>;```__   
   * Horizontal distance: positive(+) = right  /  Vertical distance: positive (+) = below  
   * If the color is not specified separately, it is the same as the font color.

__ex>__   
```
① <head> part
  h1 {
    text-shadow: 5px 4px 2px black;
  }
```
<br>
<hr>

### (4) list style   
#### ◆ list style property value
| type | description | example |
| -------- | -------- | -------- |
| disc | full circle shape | ● |
| circle | empty circle shape | ○ | 
| square | full rectangle | ■ |
| decimal | list starting from 1 | 1, 2, 3... |
| decimal-leading-zero | List of numbers with leading zero | 01, 02, 03... |
| lower-roman | List of Roman numerals and lowercase letters | ⅰ, ⅱ, ⅲ... |
| upper-roam | List of uppercase Roman numerals | Ⅰ, Ⅱ, Ⅲ... |
| lower-alpha or lower-latin | alphabet lowercase letters | a, b, c... |
| upper-alpha or upper-latin | alphabet capital letters | A, B, C... |
| none | Remove lists or numbers (space) |  |
<br>

#### ① list-style-type : Change list format  
* syntax : __```.class name { list-style-type: value; }```__
   * contraction: __```.class name { list-style: value; }```__   

__ex>__   
```
① <head> part
  <style>
    .mylist {
      list-style-type: square;
    }
  </style>
  
② apply in <body>
  <ul class="mylist">
    <li>Lehrstuhl 1</li>
    <li>Lehrstuhl 2</li>
  </ul>
```
<br>

#### ② list-style-image : Create a list from images   
* syntax : __```list-style-image: url(Image file path);```__   

__ex>__   
```
  ul {
    list-style-image: url('image/image1.png');
  }
```
<br>

#### ③ list-style-position : List indentation  
* syntax: __```list-style-position: value;```__   

#### ◆ list-style-position value
| type | description |
| -------- | -------- |
| inside | Indent the list inward |
| outside | default |
<br>

__ex>__  
```
① <head> part
  <style>
    .inside { list-style-position: inside; }
  </style>

② apply in <body>
  <ul class="inside">
    <li>first list</li>
    <li>second list</li>
  </ul>
```
<br>

#### ④ list-style simultaneously
__ex>__: When used separately  
```
  ol {
    list-style-type: lower-alpha;
    list-style-position: inside;
  }
```

__ex>__: When used simultaneously  
```
  ol {
    list-style: lower-alpha inside;
  }
```
<br>

#### ★ Apply ★
```
<style>
  a {
    text-decoration:none;
  }
  nav {
    width: 300px;
    margin: 50px 30px;
  }
  ul {
    list-style: none;
  }
  li {
    border: 1px solid #222;
    padding: 20px;
    margin: 5px;
  }
</style>
```
<br>
<hr>

### (5) table style 
#### ① Determines the position of the table title ```caption-side```   
* syntax : __```table { caption-side: value; }```__   

#### ◆ caption-side value
| type | description |
| -------- | -------- |
| top | Show title at top of table, default |
| bottom | Display title at the bottom of the table |
<br>

#### ◇ Color only part of the table list  
```
  td {
    background-color: pink;
  }
```
<br>

__ex>__   
```
① <head> part
  table {
    caption-side: bottom;
    border: 1px solid black;  → border of the entire table
  }
  td, th {
    border: 1px dotted black;  → Cell interior border (black dotted line)
    padding: 10px;             → Margin between cell border and content
    text-align: center;
  }
  td {
    background-color: black;    → Color only part of the table list
  }
  
② apply in <body>
  <table>
    <caption>table title</caption>
```
<br>

#### ② Table and cell borders combined by Border-collapse   
: At first, the table and cell borders are separated, creating a space between them, but these are combined to create a table with only one border.   
* syntax : __```border-collapse: value```__   

#### ◆ caption-side value
| type | description |
| -------- | -------- |
| collapse | Display table and cell borders combined into one |
| seperate | Show table and cell borders separately, default |
<br>

__ex>__  
```
  table {
    caption-side: bottom;
    border: 1px solid black;
    border-collapse: collapse;
  }
```
<br>
<br>

#### ③ The space between cells specified by Border-spacing   
* syntax: __```border-spacing: horizontal distance vertical distance```__

__ex>__  
```
  table {
    caption-side: bottom;
    border: 1px solid blue;
    border-spacing: 1cm 2em;
  }
```
