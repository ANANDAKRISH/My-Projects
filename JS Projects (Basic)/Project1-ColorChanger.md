# Project 1 - ColorChanger
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
We are given 4 coloured-buttons on the page. On clicking a particular-coloured button , the whole background color has to be changed to the color of that button (eg-: on clicking the "yellow" button, the whole background-color changes to "yellow") 

## Solution Code:

```javascript
const body = document.querySelector('body');
const buttons = document.querySelectorAll('.button');
console.log(buttons)

buttons.forEach(function (button) {
  button.addEventListener('click', function (e) {
    console.log(e);
    console.log(e.target);
    if (e.target.id === 'grey') {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === 'white') {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === 'blue') {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id === 'yellow') {
      body.style.backgroundColor = e.target.id;
    }
  });
});

```

## Alternate Solution Code:

```javascript
const body = document.querySelector('body');
const buttons = document.querySelectorAll('.button');

buttons.forEach(function (button) {
  button.addEventListener('click', function (e) {

    buttonClicked = e.target.id;
    switch (buttonClicked) {
      case 'grey':
        body.style.backgroundColor = e.target.id;
        break;
      case 'white':
        body.style.backgroundColor = e.target.id;
        break;
      case 'blue':
        body.style.backgroundColor = e.target.id;
        break;
      case 'yellow':
        body.style.backgroundColor = e.target.id;
        break;
        
    }
  });
});
```