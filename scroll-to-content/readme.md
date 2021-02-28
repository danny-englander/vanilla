# Scroll to Content

This code shows and example of scrolling to content when a button is clicked within a hero at the top of the page. There is also an A11y add-on to assist with keyboard navigation.

```javascript
// Define the element for the scroller.
const scroller = document.getElementById('content-scroller');

// Check for the scroller.
if (scroller) {
  scroller.addEventListener('click', function () {
    // Target the anchor to be scrolled to.
    scrollTo(document.getElementById("content-target"));
  });

  // A11y add-on.
  scroller.addEventListener("keyup", function (event) {
    if (event.key === 'Enter') {
      // Trigger the click on return.
      scroller.click();
    }
  });
}
 ```
