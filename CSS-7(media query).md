## 7. Media query
* We can apply the style we need by specifying more specific conditions. Media query helps this.
<br>
* Media query can be used in following situations.
 * When we apply styles based on specific conditions using CSS @media and @import @rules.
 * To point to specific media using the media property on <style>, <link>, <source> (en-US), and other HTML elements.

### 1) syntax :
 ```@media only|not screen and (property:value) { ... }```

 * The only or not keyword is literally placed in the position of only|not.
 * The only keyword refers to only the conditions that located behind.
 * And the not keyword refers to conditions excluding the conditions that located behind.
 * Screen is media type.

### 2) method how to apply media query

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

