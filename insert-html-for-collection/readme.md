# Insert HTML for a collection

This code loops through all elements on the page that have the class of `js-form-type-checkbox` and then checks within that to see if input type checkboxes are present. If so, we insert HTML after the checkbox.

```javascript
// Find checkboxes, add markup.
let outer_checkboxes = document.querySelectorAll('.js-form-type-checkbox');
// Loop through each matched element.
for (let i = 0; i < outer_checkboxes.length; i++) {
  // This is similar to jquery $(this).find('input.form-checkbox).
  let inner_inputs = outer_checkboxes[i].querySelectorAll("input.form-checkbox");
  // This is similar to jquery .after().
  // Since querySelectorAll returns a collection, we target with [0].
  inner_inputs[0].insertAdjacentHTML('afterend', '<span class="checkbox-toggle"><span class="checkbox-toggle__inner"></span></span>');
}
```
