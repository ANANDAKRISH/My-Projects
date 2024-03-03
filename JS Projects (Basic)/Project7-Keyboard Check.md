# Project 7 - Keyboard Check
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
Press any key on the keyboard and you will get the details of that key on the webage in a tabular format.

## Solution Code:
```javascript
const insert = document.getElementById('insert');
window.addEventListener('keydown', (e) => {
  insert.innerHTML = `
  <div class='color'>
  <table>
  <tr>
    <th>key</th>
    <th>code</th>
  </tr>

  <tr>
    <th>${e.key === ' ' ? 'space' : e.key}</th>
    <th>${e.code}</th>
  </tr>
  </table>
  </div>
  `;
});

```