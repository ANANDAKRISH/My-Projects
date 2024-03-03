# Project 5 - Disappearing Images
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
When a user clicks on an image , it needs to disappear from the webpage.

## Solution Code:
```javascript
const my_unordered_list = document.querySelector('#images');
my_unordered_list.addEventListener('click', function (e) {
  if (e.target.tagName === 'IMG') {
    let removeIt = e.target.parentNode;
    removeIt.remove();
  }
});

```