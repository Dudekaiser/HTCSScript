## 4. Advanced Selectors
### 1) link selector
* Descendant selector and child selector that apply styles to descendant elements
* The element one level below the base element is a child element, and the element one level below that element is a grandchild element.

#### (1) Descendant selector
 * syntax : give a space between Successor element and Descendant element

   __ex>__
   ```
   section p {             /*Successor element (space) Descendant element*/
   color : blue; }         /*Applies to all descendant p elements of a section element*/
   
   ```
   <br>
   
 #### (2) Child selector
 * syntax : write ">" between parent and child element
   
   __ex>__
   ```
   section > p {          /*parent element > child element*/
   ..... }                /*Applies to child p elements of the section element*/

   ```
   <br>

### 2) Adjacent sibling selectors and sibling selectors that apply styles to sibling elements

#### (1) Adjacent sibling selector
 * Select only the first sibling element among sibling elements
 * syntax : element1 + element2
   
    __ex>__
   ```
   h1 + p {              /*Select only the first p element, which is a sibling of the h1 element, and color the text in blue*/
   color : blue; }                

   ```
   <br>

#### (2) Sibling selector
 * Unlike adjacent sibling selectors, applies to all sibling elements
 * syntax : element1 ~ element2

    __ex>__
   ```
   h1 ~ p {              /*Applies to all p elements that are siblings of the h1 element, so color the text in blue*/
   color : blue; }                

   ```
   <br>

### 2) Attribute selector

| type | description | example |
| -------- | -------- | -------- |
| [attribute] | Elements with corresponding attributes | [required] |
| [attribute = value] | Element with specified attribute value | [target = _blank] |
| [attribute ~= value]| Elements containing specified attribute values (by word) | [class ~= button] |
| [attribute |= value] | Elements containing specified attribute values (including hyphens, by word) | [title |= us] |
| [attribute ^= value]| Elements starting with the specified attribute values | [title ^= eng] |  
| [attribute $= value]| Elements that end with the specified attribute values | [href $= xls] | 
| [attribute *= value]| Elements that match part of the specified attribute values | [href *= w3] | 

### 3) Pseudo-class
 * If we want to change the style when the user performs a specific action, such as clicking on a web element or hovering over the mouse pointer, use a pseudo-class selector
 
 | type | description |
 | -------- | -------- |
 | :link | Apply styles to unvisited links |
 | :visited | Apply styles to visited links |
 | :hover | Apply a style when we hover the mouse pointer over a specified element |
 | :active | Applies when the specified element is activated |
 | :focus | Apply styles when the specified element is focused |
 | :target | Apply a style to the anchor target |
 | :enabled | Apply styles when the specified element is available |
 | :disabled | Apply style when the specified element is unavailable |
 | :checked | Apply style to selected elements |
 | :not | Select and apply style when it is not a specified element |

  __ex>__
   ```
   a:link, a:visited {  /* Apply styles to unvisited and visited links */         
   ... }                

   ```
   <br>

  ### 4) Structural Pseudo-class
   * is kind of a pseudo class selector used to find elements at specific positions based on the structure of a web document and apply styles to them
    
  | type | description |
  | -------- | -------- |
  | :only-child | Select child element when there is only one child element in parent |
  | A:only-type-of | Select when there is only one A element in the parent |
  | :first-child | Selects the first child element among elements within the parent |
  | :last-child | Selects the last child element among elements within the parent |
  | A:first-of-type | Select the first element among A elements within the parent |
  | A:last-of-type | Select the last element among the A elements in the parent |
  | :nth-child(n) | Select the nth child element among all elements in the parent |
  | :nth-last-child(n) | Select the n-th child element from the end among all elements in the parent |
  | A:nth-of-type(n) | Select the n-th element among A elements in the parent |
  | A:nth-last-of-type(n) | Select the n-th element from the end among A elements in the parent |

  #### (1) Specify position using formulas
   * When we give a style to an odd number, we can use :nth-child(odd), and when we give a style to an even number, we can use :nth-child(even)

   __ex>__
   ```
   table tr:nth-of-type(2n+1) {  /* Apply style only to odd columns */
            background:black;
            color:white;
        }               

   ```
   <br>

  ### 5) Pseudo-Element
   * Pseudo class selects a desired element among several elements in a web document
   * And Pseudo element : used to style specific parts of a document
   * The reason for pseudo-element is to avoid using unnecessary tags, especially when we decorate the visible part of the screen
   * Pseudo elements are indicated by adding two colons (::) in front of the pseudo element name to distinguish them from pseudo classes

  
  | type | description |
  | -------- | -------- |
  | ::first-line | Select first line |
  | ::first-letter | Select the first letter in a line |
  | ::before | Add content or style to the front of a specific element |
  | ::after | Add content or style after a specific element |

  __ex>__
   ```
  li.new::after {
      content: "Hello world!";
      font-size: x-small;
      padding: 2px 4px;
      margin: 0 10px;
      border-radius: 2px;
      background: black;
      color: white;
    }               

   ```
   <br>
