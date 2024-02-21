# Project 3 - Digital Clock
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
Display a live digital clock on the webpage

## Solution Code:
```javascript
const clock = document.querySelector('#clock');

setInterval(function () {
  let date = new Date();
  clock.innerHTML = date.toLocaleTimeString();
}, 1000);

```

