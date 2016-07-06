# Textfit

## How to use
Download or clone the repo

Copy textFit.min.js to your vendor js directory

Include /path/to/textFit.min.js on your page

Create a new js file and add or add directly insert into html script section

```
const MULTILINE_LENGTH = 30;
var selector = 'YOUR_SELECTOR_GOES_HERE';

addLineBreaks(selector);

textFit(document.getElementsByClassName(selector), {
  multiline: true,
  alignHoriz: true,
  alignVert: true,
  minFontSize: 10,
  maxFontSize: 50
});

function addLineBreaks(selector) {
  var element = document.querySelector(selector);
  var text = element.innerText;
  if (text.length >= MULTILINE_LENGTH) {
    var res = text.split(' ');
    var middle = Math.round(res.length / 2);
    var firstHalf = res.slice(0, middle);
    firstHalf.push('<br />');
    element.innerHTML = firstHalf.concat(res.slice(middle, res.length)).join(' ');
  }
}
```
