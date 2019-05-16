# Variables: CSS Custom Properties

## Using Variables for Color  

Large websites can result in large CSS files.  Just like code refactoring we can refactor property values that
are used repeatly by assigning values to variables in CSS.  This is nice if we want to change the color of a lot of 
styles that all use the same color without having to search through all the CSS to find where to change it.   

### Color Contrast  
An import consideration in developing accessible web sites to to maintain good color contrast.  The settings for the `color` and `background-color` properties for an element are good candidates for assignment to variables.  When coded together, it's easier to guarateen that a high contrast will be maintained.  

There are tools to help with choosing high contrast color pairs.  For example the website [Contrast Checker](https://contrastchecker.com/) will help to ensure that you are maintaining high contrast in your website.  See also [Color Safe](http://colorsafe.co/) for finding recommended colors.  You want a ratio of r 4.5 for small text (less than 18px) and 3 for large text (greater than 18 pixels).  You can find more information about this here: [Web AIM](https://webaim.org/blog/wcag-2-0-and-link-colors/).  

### Use Variables  
In this assignment, you'll use CSS variables to create custom color pairs for a set of 5 containers.  You'll assign one pair to the odd numbered container and the other pair to the even number of containers.  CSS will help you identify odd and even containers.  

1. You'll find an index.html file with an unordered list of numbers 1-5.  Add a style sheet to the index.html.
2. Layout the containers horizontally and provide dimension and style.
  - Set box-sizing to border-box
  - Set the body height to `100vh`.  `vh` is the **view height** unit and 100 vh indicates 100% of the visible screen.
  ```
  *  {
    box-sizing: border-box;
  }
  body {
      height: 100vh;
    }
  ```
  - Set the unordered list to 80% wide and 10 rem high.  Center its contents horizontally by providing `{margin: 5rem auto}`.  This gives a top and bottom margin or 5rem's and equal margins on both and left right of the block element. Set `list-style-type` to none to remove bullets
  ```
   ul {
      width: 80%;
      height: 10rem;
       /*center horizontally */
      margin: 5rem auto;
      padding: 0;
      list-style-type:none;    
    }
  ```
  - For the list items, 
    - center the text horizontally with `text-align` and center them vertically by using 10 rem's for both `height` and `line-height`.
    - apply font properties: size `24px`, family `Arial, Helvetica, sans-serif` and weight `400`
    - display `inline-block` to render the items horizontally
    - provide a border of `1px`, `solid`, `darkgray`
    - set the width of each item to `19%` (We have 5 items which we want to fill 80% of total horizontal width, but we have a border, so we neeed to leave make the width a little under 20%)
    ```
    li {
      text-align: center;
      font-size: 24px;
      font-family: Arial, Helvetica, sans-serif;
      font-weight: 400;
      display: inline-block;
      height: 10rem;
      line-height: 10rem;
      width: 19%; 
      border: 1px solid darkgray;
    }
    ```
3. Use a high contrast color selector tool to choose a pair of color for the odd containers. You'll use black and white for the even containers.  Create custom variables for odd and even foreground and background colors that apply to the whole page using the following CSS code which uses the `:root` pseudo selector:
```
 :root {
      --odd-color: #d46843;
      --odd-bg-color:#2A150D;

      --even-color: white;
      --even-bg-color: black;
    }
```   
4. Apply the even colors to the even list items using this code which takes advantage of the `nth-child(even)` pseudo selector:
```
 li:nth-child(even) {
      color: var(--even-color);
      color: var(--even-bg-color);
    }
```  
Apply odd colors to the odd list items using this code:
```
 li:nth-child(odd) {
      color: var(--odd-color);
      background-color: var(--odd-bg-color);
    }
```  

### Solution  

Solutions shows layout but the odd colors may vary.  
![CSS variables solution](images/skills-2-css-variables.png)







