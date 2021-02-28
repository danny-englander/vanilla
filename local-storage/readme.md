# Local Storage

The code below shows an example of maintaining the state HTML classes on the page. There are two buttons, `solid` and `outline` and when either button is clicked, the classes on the page change and the state of the classes remains as is even with a page reload. This seems to be a better method than using cookies for this type of thing.

The main concepts here are setting the local storage state with:

```javascript
localStorage.setItem('iconState', 'outline_icon');
localStorage.setItem('iconState', 'solid_icon');
```

## Full code below

```javascript
     // Define variables for adding and removing classes
// and using local storage to maintain the state.
const outline_trigger = document.querySelector("#trigger-outline");
const solid_trigger = document.querySelector("#trigger-solid");
const body = document.querySelector("body");
const icon_item = document.querySelectorAll('.icon-item__icon.material-icons'); // Test to check the state of local storage.

if (localStorage.getItem('iconState') === 'outline_icon') {
  // Add a class if it's outline.
  body.classList.add("has-outline-icons");
  icon_item.forEach(element => element.classList.add('material-icons-outlined'));
  icon_item.forEach(element => element.classList.remove('material-icons'));
}

if (solid_trigger) {
  // Click action for the solid button.
  solid_trigger.addEventListener("click", function () {
    // console.log('solid')
    localStorage.setItem('iconState', 'solid_icon');
    body.classList.remove("has-outline-icons");
    icon_item.forEach(element => element.classList.remove('material-icons-outlined'));
    icon_item.forEach(element => element.classList.add('material-icons'));
  }, false);
}

if (outline_trigger) {
  // Click action for the outline button.
  outline_trigger.addEventListener("click", function () {
    //  console.log('outline')
    body.classList.add("has-outline-icons");
    localStorage.setItem('iconState', 'outline_icon');
    icon_item.forEach(element => element.classList.add('material-icons-outlined'));
    icon_item.forEach(element => element.classList.remove('material-icons'));
  }, false);
}
```
