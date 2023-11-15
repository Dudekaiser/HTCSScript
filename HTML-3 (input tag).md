## 3. html input form
### 1) form
### (4) Main attributes of input tag
| type | description |
| -------- | -------- |
| required | Display status window when no input |
| pattern | Set the pattern to input according to the specified pattern |
| readonly | Only for read text |
| autofocus | Automatically position the cursor |
| placeholder | Display hint in input box |
| select, option | Create selected content |

#### ① required
: A status window is displayed, when a value is submitted without value.
```
<p>
  <label>password : <input type="password" required></label>
  <input type="submit" value="Log-in">
</p>
```

#### ② pattern
: When a value that does not fit the format is entered, an error message window is displayed.
```
<p>
  <label for="phone">contact : </label>
  <input id="phone" type="tel" pattern="[0-9]{4}-[0-9]{4}-[0-9]{3}">
</p>
```
<br>

#### ③ readonly   
: Create text that cannot be erased by the user and is only readable 
* syntax : ```<input type=text-input-field readonly>```

__ex>__   
```
  <label for="prod">order product</label>
  <input type="text" id="prod" value="For sale 3KG" readonly>   
```
<br>

#### ④ autofocus
: Automatically position the cursor   
```
  <label for="user-name">title </label>
  <input type="text" id="user-name" required autofocus>
```

#### ⑤ placeholder   
: Display hint content in input box  

```
  <label for="uid">id</label>
  <input type="text" id="uid" autofocus placeholder="Between 4 and 10 characters, no spaces" required>
  <label for="pwd">password</label>
  <input type="password" id="pwd" placeholder="Contains letters, numbers and special symbols" required> 
```
<br>
<hr>

#### ⑥-1 select / option   
: __```value```__ : Value to be sent to the server   
: __```slected```__ : First shown option  
: __```multiple```__ : When we select two or more options

__ex1>__   
```
  <select>
    <option value="gift_3" selected>For gift 3kg</option>
    <option value="gift_5">For gift 5kg</option>
    <option value="fam_3">For family 3kg</option>
  </select>
```

__ex2>__   
```
  <select name="drink" multiple>
    <option value="1" selected>water</option>
    <option value="2">coke</option>
    <option value="3">fanta</option>
  </select>
```
<br>

#### ⑥-2 datalist
* syntax :   
```
  <input type="text" list="data list id">
  <datalist id="data list id">
    <option value="Value to pass to server1">option1</option>
    <option value="Value to pass to server2">option2</option>
  </datalist>
```
<br>

__◆ Difference between select and datalist__
* Can be found by searching among hundreds of options  
* There is a risk of entering an incorrect value that is not in the option. 
* Takes up less memory and is faster than dozens of select boxes  
