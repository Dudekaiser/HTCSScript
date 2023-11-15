### HTML

## 1. html structure
* IF i want to write language with korean, use 
```<html lang = "ko">```
* For english, "en".

### 1) HEAD Tag : Not displayed but it is needed for interpretation of web document.
  * ```<meta charset = "UTF-8">``` : to address ASCII and we can translate almost every language. So if the font is broken, we use this.
  * ```<title> INHALT </title>``` : Name of Title
<br>

### 2) BODY Tag : Contents on the Screen
```
<body>
  <h1> let's Create Web document </h1>
<body>
```

### (1) Contents Tag
* Title Tag : ```<hn> title </hn>```
: The smaller the number of n, the smaller the size. h1 > h2 > h3 > ...

* Create Paragraph : ```<p> content </p>```
* Enter : ```<br>```
* Highlight : ```<strong> content </strong>```
* Bold : ```<b> content </b>```
* Slant(emphasis) : ```<em> content </em>```
* Horizontal line : ```<hr>```
<br>
<hr>

### (2) List
* ordered list : ```<ol> ordered list </ol>```
  * ```<ol type = "a"> content </ol>``` : list of a, b, c
  * unordered list : ```<ul> content </ul>```
  * Items in "ol" : ```<ol> <li> content </li> </ol>```
<br>
<hr>

### (3) Create Table
  * Syntax : ```<table> content </table>```
  * Title of table : ```<caption> title </caption>```
  * row : ```<tr> </tr>```
  * column : ```<td> </td>``` , ```<th> </th>```

```
 <table>
    <caption>title of table</caption>
    <tr>
        <th>1.row 1.column</th>
        <th>1.row 2.column</th>
    </tr>
    <tr>
        <td>2.row 1.column</td>
        <td>2.row 2.column</td>
    </tr>
  </table>
```
* table border
```
<style>
    table {
        border:1px solid #ccc;
        border-collapse: collapse;
    }
    td, th{
        border:1px solid #ccc;
        padding:10px;
    }
```
<br>
<hr>

### (4-1) Insert Image
 * Syntax :
 __```<img src="path" alt="alternative">```__   
 : alternative : Text for the visually impaired

 * Images in subfolders  
 ```<img src="subfolder/path" alt="alternative">```    
 <br>

 * adjust size (width, height)

 | type | description | example |
 | -------- | :------: | -------- |
 | %  | Decision based on web browser window | width="50%" |
 |px  | display as per pixel size | width="150" |

 <br>

 ### (4-2) Audio
  * Syntax 
  __```<audio src="path audio directory"></audio>```__

  * play bar (controls)   
  ```<audio src="오디오 파일 경로" controls></audio>```

  * adjust the size : width and height using px
  <br>

 ### (4-3) Video
 * syntax   
 __```<video src="path video"></video>```__   

 * play bar (controls) same as Audio   
 * adjust size as well (width, height)
 <br>

* audio, video TAG

| type | description |
| -------- | -------- |
| autoplay | automatically played |
| loop | repeat play |
| muted | sound removal |
| poster="file name" | video thumbnail photo |

```
ex>
<audio src="file path" autoplay loop poster="file name"></audio>
```
<br>

### (4-4) embed
: Insert various multimedia such as audio, video, and images etc.
__```<embed src="파일 경로" width="너비" height="높이">```__   

ex>
```
<embed src="media/rwth.mp4" controls width="100" height="50">
```
<br>
<hr>
  
### (5) Hyperlink
* syntax   
__```<a href="link address">text or image</a>```__
<br>

* text link   
```
<div>
  <p><a href="link">text</a></p>
</div>
```

* image link
```
<a href="link"<img src="image address" alt="alternative text"></a>
```

* ex>   
```
<div id="container">
  <a href="index.html"><img src="images/RWTH.jpg" alt="rwth aachen" width="300"></a>
  <p><a href="embed.html">Let's insert multimedia</a></p>
</div>
```

* Opens in new tab   
: __```target="_blank"```__
```
<div>
  <p><a href="link" target="_blank"> text </a></p>
```







