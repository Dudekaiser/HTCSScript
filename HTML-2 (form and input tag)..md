## 2. html input form
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

#### ① Transfer/Reset Button
__◇ "Transfer Button" submit__   
: Button to transmit the entered information to the server  
* syntax : __```<input type="submit" value="button title">```__   
<br>

__◇ "reset Button" reset__   
: Button to reset entered information   
* syntax : __```<input type="reset" value="button title">```__   
<br>

__ex>__   
```
<div>
  <input type="submit" value="Go order">
  <input type="reset" value="Calcel">
</div> 
```
<br>   
<hr>   

#### ②-1 checkbox
: Options (multiple choices available)
```
<label for="color_blue">
  <input id="color_blue" type="checkbox" value="blue"> blue
</label>
<label for="color_red">
  <input id="color_red" type="checkbox" value="red"> red
</label>
```

#### ②-2 radio
* Option (only 1 can be selected)   
: __```name```__ : Name to be sent to server   
: __```value```__ : Value to be sent to server
```
<p><b>Packaging Selection</b></p>
<label><input type="radio" name="gift" value="yes">gift wrapping</label>
<label><input type="radio" name="gift" value="no">No gift wrapping</label>
```

* __```checked```__   
: Be a "DEFAULT Value" automatically among options(Checked in check box)   
```
  <legend>Events and News</legend>
  <input type="radio" name="mailing" id="mailing_y" value="mailing_yes">
  <label for="mailing_y">Receive mail</label>
  <input type="radio" name="mailing" id="mailing_n" value="mailing_no" checked>
  <label for="mailing_n">Not receiving mail</label>  
```

<br>   
<hr> 

#### ③-1 number
: Adjust the number with the arrows
```
<p><u1>
  <li>
    <label>For gitf 3kg <input type="number" min="0" max="5" value="1"> 1 (Maximum 5)</label>
  </li>
</ul></p>
```

#### ③-2 range
: Adjust the number with the bar
```
<p><u1>
  <li>
    <label>For gift 3kg <input type="range" min="0" max="5" value="1"> 1 (Maximum 5) </label>
  </li>
</ul></p>
```

* __number / range property__   

| type | description |
| -------- | -------- |
| min | Minimum value |
| max | Maximum value |
| value | default value |

<br>
<hr>

#### ④ Date/Time/Range
: user time

| type | description |
| -------- | -------- |
| date | Date (Year, Month, Day) |
| month | Date (Year, Month) |
| week | Date (year, week) |
| time | Time (hours, minutes, seconds, split seconds) |
| datetime | International standard time (year, month, day, hour, minute, second, fractional second) |
| datetime-local | Time (year, month, day, hour, minute, second, split second) |
<br>

* __DATE__

```
<h1>Setting the date</h1>
<input type="date">
<input type="month">
<input type="week">
```

* __Time__

```
<h1>Setting the time</h1>
<input type="time">
<input type="datetime-local">
```

* __Limit the scope__
```
<h1>Limit the scope</h1>
<input type="date" min="2023-01-01" max="2023-12-31">
<input type="time" min="00:00" max="23:59"
```

<br>
<hr>

#### ⑤-1 Create Button
* __Create Button 1__   
   * syntax : __```<input type="button" value="description in button">```__   
   * javascript function ```window.open()```   

__ex>__   
```
<form>
  <input type="button" value="Open notice window" onclick="window.open('notiz.html')">
</form>
```
<br>

* __Create Button 2__
  * syntax :   
```
  <button type="submit">content</button>
  <button type="reset">content</button>
  <button type="button">content</button>
```

  * Same as "Create Button 1"
  * ```type="button"``` : button without function
<br>

#### ⑤-2 Create image button
   * syntax : __```<input type="image" src="image path" alt="alternative text">```__   

__ex>__   
```
<fieldset>
  <label>id: <input type="text" id="user_id" size="10"></label>
  <label>pw: <input type="password" id="user_pw" size="10"></label>
  <input type="image" src="images/login.png" alt="login">
</fieldset>
```
<br>

#### ⑤-3 Create file attachment button
   * syntax : __```<input type="file">```__   

__ex>__   
```
<fieldset>
  <legend>Return Information</legend>
  <p>If there is a problem with the product you received, immediately <b>Request for return</b>Please.</p>
  <p>When requesting a return, please attach a photo of the condition of the product..</p>
  <hr>
  <input type="file">    
</fieldset>
```

<br>
<hr>

#### ⑥ hidden
: Information that is not visible on the screen but is transmitted to the server
ex> Membership registration time, region, entry route, etc.
<br>

* syntax : __```<input type="hidden" name="name" value="Value to send to server">```__   

__ex>__
```
  <input type="hidden" name="url" id="url" value="Log in directly through the site">
  <label>id: <input type="text" id="user_id" size="10"></label>
  <label>pw: <input type="password" id="user_pw" size="10"></label>
  <input type="submit" value="log-in">
```
