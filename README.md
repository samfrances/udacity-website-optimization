# Website Performance Optimization portfolio project

For more information on the specification of the project, see [spec.md](spec.md).

## Optimizations

- Relating to [index.html](index.html)
 + Added async attribute to google analytics script tag.
 + Added print media query to print css.
 + Inlined main stylesheet.
 + Removed Open Sans web font.
 + Scaled down pizzeria image used in index.html.
- Relating to [views/js/main.js](views/js/main.js)
 - Use `requestAnimationFrame` to wrap `updatePositions` before passing to the scroll event listener.
 - In `updatePositions`, move line `var scrolltop = document.body.scrollTop / 1250;` outside
   of the for loop for avoid triggering forced synchronous layouts.