# Project 2 - BMI Generator
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
Calculate BMI from the input fields : height & weight

## Solution Code:
```javascript
const form = document.querySelector('form');

form.addEventListener('submit', function (e) {
  e.preventDefault();

  const height = parseInt(document.getElementById('height').value);
  const weight = parseInt(document.getElementById('weight').value);
  const result = document.getElementById('results');

  if (height < 0 || isNaN(height)) {
    result.innerHTML = `Provide a valid height . Given value is : ${height}`;
  } else if (weight < 0 || isNaN(weight)) {
    result.innerHTML = `Provide a valid weight . Given valus is : ${weight}`;
  } else {
    const bmi = (weight / ((height * height) / 10000)).toFixed(2);
    let status = '';
    if (bmi < 18.6) {
      status = 'Underweight';
    } else if (bmi >= 18.6 && bmi < 24.9) {
      status = 'Normal';
    } else {
      status = 'Overweight';
    }
    result.innerHTML = `<span> Bmi value = ${bmi}. You are ${status} </span>`;
  }
});
```