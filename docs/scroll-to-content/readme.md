# Scroll to Content

This code shows and example of scrolling to content when a button is clicked within a hero at the top of the page. There is also an A11y add-on to assist with keyboard navigation.

```javascript
// Define the scroller elements.
const scroller = document.getElementById('content-scroller');
const scroller_target = document.getElementById("content-target")
// Check for the scroller.
if (scroller) {
  scroller.addEventListener('click', function () {
    // Target the anchor to be scrolled to.
    scrollTo(scroller_target);
  });

  // A11y add-on.
  scroller.addEventListener("keyup", function (event) {
    if (event.key === 'Enter') {
      // Trigger the click on return.
      scroller.click();
    }
  });
}

// Custom scrollTo function.
  scrollTo = (element) => {
    window.scroll({
      behavior: 'smooth',
      left: 0,
      top: element.offsetTop
    });
  };
 ```
