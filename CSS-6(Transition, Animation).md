## 6. Transition :vs: Animation
 * Both can express movement, but there is a difference.

<br>

### 1) Transition
 * Changes the shape of an element by twisting, rotating, moving, or changing color
 * Transition occurs changes of elements **during a certain period**
 * **Operates by event trigger**, such as `hover` or `click`
 * When we change the layout, it is recommended to apply effects to low-level elements in order to reduce reflow
 <br>

#### (1) Transition property

| property | description | default |
|---|---|---|
|transition-property| Specify the CSS property that is the target of the transition | all |
|transition-duration| Specify the duration of the transition in seconds | 0s |
|transition-timing-function| Specify a numerical function for the transition effect | ease |
|transition-delay| Specify the time to wait in seconds between when a property changes and when the transition actually starts. | 0s |
|transition| Specify all transition properties at once (shorthand) |  |

* Specify the CSS property name that is the target of the transition. If not specified, all properties are subject to transition. If more than one is specified, separate them with commas

__ex>__ 
```css
div{
  transition-property: width, background-color;
  }
/* This means that the transition is applied only to width and background-color. */
```
<br>

* Not all css properties can be the target of ```transition```. Can be applied to changed value within a category, such as shape, color, size (```color```, ```font```, ```width```), but such as ```display``` does not apply to properties that change the essence
* The properties to which transitions can be applied as following : 
```html
// box model
width height max-width max-height min-width min-height
padding margin
border-color border-width border-spacing

// background
background-color background-position

// coordinate
top left right bottom

// text
color font-size font-weight letter-spacing line-height
text-indent text-shadow vertical-align word-spacing

// etc.
opacity outline-color outline-offset outline-width
visibility z-index
```
* Transition effects that affect layout place significant stress on the browser and cause performance degradation 
* Therefore, it is best to avoid transition effects that affect the layout 

* Properties that affect layout are as follows
```html
width height padding margin border
display position float overflow
top left right bottom
font-size font-family font-weight
text-align vertical-align line-height
clear white-space
```
<br>

#### (2) transition-duration
 * Specifies the **duration (duration) of the transition in seconds**. **If the property value is not specified, the default value is 0s so no transition effect is visible.**

 __ex>__
 ```css
 div {
  transition-property: width, opacity;
  transition-duration: 2s, 4s;
 }
 ```

 * We can express with only ```transition``` propterty

  __ex>__
 ```css
 div {
  /* shorthand syntax */
  transition: width 2s, opacity 4s;
 }
 ```
 <br>

 #### (3) transition-timing-function
 * Specify a kind of rhythm of change, such as the flow of change in a transition effect or the speed of change over time. (acceleration time)

 | Property | Effect | 
 |------|---|
 | ease | Default. Starts slow, gets faster, then slows down to end |
 | linear | Uniform speed movement from start to finish |
 | ease-in | Start slowly, then move at a uniform speed when you reach a certain speed. |
 | ease-out | Starts at a uniform speed and ends at a gradual slowdown |
 | ease-in-out | Start slow, end slowly |

 #### (4) transition-delay
  * Specifies the waiting time in seconds between when a property changes and when the transition actually starts
  * by specifying the waiting period with transition-delay, the transition is not executed immediately even if the property changes, but the transition is executed after waiting for a certain period of time
 
  __ex>__
  ```css
  selector {
    transition-delay: 1s;
    }
  ```
 <br>

 ### (5) transition-shorthand
  * It is a shorthand that allows us to specify all transition properties at once
  * Default values are assigned to properties that do not specify a value 

  __ex>__
  ```css
  selector {
    transition: property duration function delay;
    }
  ```
  <br>
  
  * ```trainsition-duration``` must be specified 
  * IF not specified, the default value is set to 0 and no transition is executed

  ---
  When we use ``transition````, we must remember the following two things:

  * It does not activate automatically
  * Where should we place it?  

---

<br>

### 2) Animation
 * Transition requires an event to start, but animation can controll to start, stop, and repeat (of course, event control is also possible).
 * It starts automatically and can be played infinitely.
 * Consists of one or multiple **`@keyframes`**
 * using CSS animation provides better rendering performance compared to Javascript-based animation execution
 * Most frameworks, including jQuery, react, and angular, provide animation functions to make them easier to use than CSS.
 * For example, animation for element's width adjustment is much simpler and more effective than using JavaScript.
 * For detailed control, it is preferable to use JavaScript. For example, JavaScript is much more useful for advanced effects such as bounce, stop, pause, rewind, or slow down.
 <br>

 #### (1) @keyframes
  * Using this @keyframes, we can specify CSS property values at various breakpoints during the animation sequence

  __ex>__
  ```css
  @keyframes move {
    /* When animation starts */
    from { left: 0; }
    /* When animation ends */
    to   { left: 300px; }
  }
  ```
 <br>

  * % can be used instead of from and to keywords
  * We can also insert keyframes in % between the start and end keyframes.

  __ex>__
  ```css
  @keyframes move {
    0%   { left: 0; }
    50%  { left: 100px; }
    100% { left: 300px; }
  }
  ```

 #### 2) animation-name
  * In the example, @keyframes is followed by a random name representing the animation.

   __ex>__
  ```css
  @keyframes move {}
  ```
   Select the @keyframes rule you want to use by specifying this name as the animation-name property value.
   We can specify more than one animation name.
  ```html
  <!DOCTYPE html>
  <html>
  <head>
    <style>
      div {
        position: absolute;
        width: 100px;
        height: 100px;
        animation-name: move, fadeOut, changeColor;
        animation-duration: 5s;
        animation-iteration-count: infinite;
      }
      @keyframes move {
        from { left: 0; }
        to   { left: 300px; }
      }
      @keyframes fadeOut {
        from { opacity: 1; }
        to   { opacity: 0; }
      }
      @keyframes changeColor {
        from { background-color: red; }
        to   { background-color: blue; }
      }
    </style>
  </head>
  <body>
    <div></div>
  </body>
  </html>
  ```
  <br>
  
#### 3) animation-duration
 * Specifies the time required for one cycle of animation in seconds.

  ```css
  animation-duration: 5s;
  ```
  <br>

#### 4) animation-timing-function
 : Specifies a numerical function for animation effects
   
  * ```ease(default)```: Default. Starts slow, gets faster, then slows down to end
  * ```linear```: Uniform speed movement from start to finish
  * ```ease-in```: Start slowly, and when a certain speed is reached, move at a uniform speed
  * ```ease-out```: Starts at a uniform speed and ends at a gradual slowdown
  * ```ease-in-out```: Similar to "ease", it starts slowly and ends slowly.

#### 5) animation-delay
 * Specifies the number of seconds to wait between when an element is loaded and when the animation actually starts.

  ```css
  animation-delay: 2s;
  ```

#### 6) animation-iteration-count
  * Number of times the animation will repeat. The default value is 1 and can be infinitely repeated.

  ```css
  animation-iteration-count: 3;
  ```

### 7) animation-direction
  * Specifies the direction in which the animation progresses when it repeats after it ends

  ***property values***
  * ```normal(default)```: Default value, proceeds from from(0%) to to(100%). 
  * ```reverse```: progressed to -> from (opposite of normal)
  * ```alternate```: Odd numbers proceed as normal, even numbers proceed as reverse
  * ```alternate-reverse```: Odd numbers proceed to reverse, even numbers proceed to normal

### 8) animation-fill-mode
 *  Specifies the style of the element when the animation is not running (waiting or ending)

  ***property values***
  * ```none```
    * Wait: Wait without applying the style set to the starting frame (from)
    * End: Restore to the state before animation execution
  * ```forwards```
    * Wait: Wait without applying the style set to the starting frame (from)
    * End: End with the style set in the end frame (to) applied
  * ```backwards```
    * Wait: Apply the style set to the start frame (from) and wait.
    * End: Return the property values of animation elements to the state before animation execution and end.
  * ```both```
    * Wait: Apply the style set to the start frame (from) and wait.
    * End: Apply the style set to the end frame (to) and end.

### 9) animation-play-state
 * Specifies the animation playback state (playing or stopped). The default is running.
   
  ```css
    div:hover {
      background: blue;
        animation-play-state: paused;
      }
      div:active {
        background: yellow;
        animation-play-state: running;
      }
  ```
### 10) animation shorthand
 * Specify all animation properties at once. If no value is specified, a default value is specified.

  ```css
  selector{
  animation: name duration timing-function delay iteration-count direction fill-mode play-state;
  }
  ```
  
  ---
***notice***  
 ````duration```` must be specified as required.
 If not specified, the default value is set to 0 and the animation is not executed.

---

<br>

### 3) Transform

* Provides functions to apply movement, rotation, zoom, and twist effects to elements.
* It is applied and displayed immediately on the screen.
* Not intended for animation effects (use with transitions or animations when necessary)
