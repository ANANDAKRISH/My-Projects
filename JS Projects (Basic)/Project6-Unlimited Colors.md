# Project 6 - Unlimited Colors
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
When you click on the start button , the background color needs to start changing continously in a fixed interval and when you click on the stop button , this process needs to stop.

## Solution Code:
```javascript
const randomColor = function () {
  const hex = '0123456789ABCDEF';
  let hexCode = '#';
  for (let i = 0; i < 6; i++) {
    hexCode += hex[Math.floor(Math.random() * 16)];
  }
  console.log(hexCode);
  return hexCode;
};

let intervalColor;
const startChangingBackground = function () {
  const changeColor = function () {
    document.body.style.backgroundColor = randomColor();
  };
  if (!intervalColor) {
    intervalColor = setInterval(changeColor, 1000);
  }
};

const stopChangingBackground = function () {
  clearInterval(intervalColor);
  intervalColor = null;
};

document
  .querySelector('#start')
  .addEventListener('click', startChangingBackground);
document
  .querySelector('#stop')
  .addEventListener('click', stopChangingBackground);
```

## Alternate solution:
```javascript
const randomColor = function () {
  const hex = '0123456789ABCDEF';
  let hexCode = '#';
  for (let i = 0; i < 6; i++) {
    hexCode += hex[Math.floor(Math.random() * 16)];
  }
  console.log(hexCode);
  return hexCode;
};

const startButton = document.querySelector('#start');
const stopButton = document.querySelector('#stop');
stopButton.setAttribute('disabled', '');

let intervalColor;
const startChangingBackground = function () {
  const changeColor = function () {
    document.body.style.backgroundColor = randomColor();
  };

  intervalColor = setInterval(changeColor, 1000);
  startButton.setAttribute('disabled', '');
  stopButton.removeAttribute('disabled');
};

const stopChangingBackground = function () {
  clearInterval(intervalColor);
  startButton.removeAttribute('disabled');
  stopButton.setAttribute('disabled', '');
};

startButton.addEventListener('click', startChangingBackground);
stopButton.addEventListener('click', stopChangingBackground);

```