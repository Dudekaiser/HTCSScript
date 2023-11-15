## 3. html input form
### 1) form
* syntax   
```<form [property="property value"]> form elements </form>```
<br>

### (1) ```form action=""```   
: When we send data to the server
```
ex> If we send login value..
<form action="http://localhost/login.php">
```

### (2) ```fieldset```, ```legend``` 태그
: Input form with border

#### ① fieldset
: Create group box border

#### ② legend
: Create group box title

* syntax
```
<form action="">
  <fieldset>
    <legend> group title </legend>
  </fieldset>
```

<br>   
<hr>

### 2) input tag
: When we want to do "typing" something.

### (1) ID, PASSWORD
* __```text```__ : Enter one-line text
* __```password```__ : Hides the entered password
```
<form action="">
    <p>id : <input type="text"></p>
    <p>password : <input type="password"></p>
</form>
```
<br>

* __```textarea```__ : multi-line input  
: ```cols``` : number of characters  
: ```rows``` : number of lines   

__ex>__
```
  <label for="memo"> memo </label>
  <textarea id="memo" cols="40" rows="4"></textarea>
```
<br>

### (2) Label
: To indicate that something is a __"name tag"__
→ When you press the ID or password text, the cursor will appear there.
```
ex1>
    <label>id : <input type="text"></label>
    <label>password : <input type="password"></label>
```
<br>

* When using label TAG and form element separately
__```<label for="id name"> label name </label>```__   
__```<input id="id name">```__

```
ex1>
    <label> for="user-id"> id : </label>
    <input id="user-id" type="text">
```
<br>

* __```submit```__ : Submit (Send) button   
```<input type="submit" value="button title">```
<br>

### (3) Various input tags
| Type | Description |
| -------- | -------- |
| search | search box |
| url | Enter url address |
| email | Enter email address |
| tel | Enter phone number |
| submit | send button |
| reset | reset button|
| checkbox | Create two or more selectable boxes |
| radio | Create a selection box where only one item can be selected |
| number, range | Adjust the number with arrows (bars) |
| date, month, week, time | date, time |
| button | Create Button |
| image | Create image button |
| file | Create file attachment button |
| hidden | Information that is not visible on the screen but is transmitted to the server |
<br>

