# Project 8 - XHR
### Project Link : [Click Here](https://stackblitz.com/edit/stackblitz-starters-drvbqn?file=Project%201%20-%20ColorChanger%2Fscript.js)

## Problem : 
You need to fetch some details from the given requestURL using XHR & display those on the webpage. Create a button to access these details.

## Solution Code:
```javascript
const requestURL = 'https://api.github.com/users/hiteshchoudhary';
    const xhr = new XMLHttpRequest();
    xhr.open('GET', requestURL);
    xhr.onreadystatechange = function () {
      if (this.readyState === 4) {
        const data = JSON.parse(this.responseText);
        const followers = data.followers;
        const bio = data.bio;
        const login = data.login;
        const img = data.avatar_url;
        console.log(data);
        const body = document.querySelector('body');
        const div = document.createElement('div');
        body.appendChild(div);
        div.innerHTML = `<img src="${img}" alt="Htesh Image" width="500px">`;
        const button = document.createElement('button');
        button.innerHTML = 'Know My Details';
        body.appendChild(button);
        button.addEventListener('click', function (e) {
          const div2 = document.createElement('div');
          body.appendChild(div2);
          div2.innerHTML = `1. Login Name : ${login} <br> 2. Bio : ${bio} <br> 3. Followers Count: ${followers} `;
        });
      }
    };
    xhr.send();

```
