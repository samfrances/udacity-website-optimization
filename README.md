# Website Performance Optimization portfolio project

For more information on the specification of the project, see [spec.md](spec.md).

## Optimizations

- Relating to [index.html](index.html)
 + Add async attribute to google analytics script tag.
 + Add print media query to print css.
 + Inline main stylesheet.
 + Remove Open Sans web font.
 + Scale down pizzeria image used in index.html.
- Relating to [views/js/main.js](views/js/main.js)
 + General
    - Factor out querySelector and querySelectorAll.
 + Scrolling
    - Use `requestAnimationFrame` to wrap `updatePositions` before passing to the scroll event listener.
    - In `updatePositions`, move line `var scrolltop = document.body.scrollTop / 1250;` outside
    of the for loop for avoid triggering forced synchronous layouts.
    - Add `will-change: left;` to `.mover` css class to create compositor layers for moving background pizzas.
        - For older browsers: `transform: translateZ(0);`
    - Reduce the number of moving pizzas to 48
 + Resizing pizzas
    - Remove `determineDx` function and replaced with simple percentage sizes.
    - Resolve forced synchronous layouts relating to for-loop in `changePizzaSizes` function.
    - Move repeated query for `.randomPizzaContainer` out of for-loop in `changePizzaSizes` function.
