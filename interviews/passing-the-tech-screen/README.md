# Tech Screen Interview Questions

## CSS

1. What are CSS selectors?

Just points to the element(s) you want to style. A selector has a property and a value.

1. What is selector specificity?
1. What is the difference between selectors `.class1.class2` and `.class1 .class2` (space added)?
1. How about these selectors `.class1 .class2` and `.class1 > .class2`?
1. And these selectors `.header .nav a` and `.header a`?
1. How do you center something in CSS?
1. What is SASS/LESS/Stylus/etc?
1. What is component based SCSS/CSS? 
1. ~~How do floats work?~~
1. How do you get something to not display using CSS?
1. Why would you use Flexbox or CSS Grid?

Flexbox is either rows or columns. Grid is generally for both. 

## JavaScript

1. Where can you use JS?

_Mostly client side, but there is server-side JavaScript like Node._

1. What is NodeJS?

_Back-end Javascript built on Chrome's V8 engine._

1. Does it have/use types?

_Yes. Node elements have a NodeType of 1, attribute is 2, text, is 3, comment is 8._ 

1. Name 2 or more ES6 features.

_Arrow functions, and classes - previously had to use prototypes._ 

1. What are `let` and `const`?

_ES6 Ways to define a variable. Let is scoped to the block, const means it's immutable._ 

1. What is `var`?

_Declares a variable._ 

1. How is `var` different than `const`?

_Const says it won't be reassigned and is es6._ 

1. What are anonymous functions?

_Functions that don't have a name. so instead of `function letterCount(){}` it would be `function (){}`._

1. How do you define a global variable?

_Just declare a variable outside of a function._ 

1. How do you define a global variable inside of a function?

_Docs aren't clear on this. You could use the window object and do `window.foo = 90;`. OR you could assign a value to a variable inside a function that hasn't been declared at all yet - so inside the function, instead of `var foo = 90;` you simply write `foo = 90;`._ 

1. What does IIFE (pronounced iffy) mean?

_Immediately invoked function expression. It runs as soon as it's defined._ 

1. What is a higher order function?

_Functions that take functions as arguments or return functions. Functions that interate over arrays and return a modified version of it._ 

1. Why are functions in JavaScript 'first class'?

_Because they can have properties and methods just like any other object._ 

1. What's a closure?

_An inner function that has access to the outer function's variables. It has access to its own scope, the outer function's scope, and the global scope._ 

1. What is the difference between `==` and `===`?

_Equals vs strict equals. `==` compares value, `===` compares value and type. So `2 == '2' == true`, but `2 === '2' = false`._

1. What is the difference between `null` and `undefined`?

_Undefined means a variable has been declared but not assigned a value. Null is an assignment. Also, null is an object. By the way, when you declare a variable like `var foo;` you aren't assigning it a value, but it does get initialized with `undefined`._ 

1. What are the primitive data types?

_Null, undefined, boolean, string, number._ 

1. How does event bubbling work?

_If you clicked on a p that was nested inside a div that was inside a form, even if the click handler was on the p, it would bubble up to the form, then the div._ 

1. How do you avoid event bubbling?

_event.stopPropogation();_

## React:

1. What is one lifecycle hook that is in every class component?
constructor
1. Name as many lifecycle hooks as you can?
componentDidMount, componentWillMount, render
    1. Bonus: Name the deprecated hooks.
1. What is the difference between state and props?

1. Can you set state more than once?
1. How does React use the virtual DOM?
1. What are the pros/cons w/ `css-in-js`?
1. Why do we typically need to use babel?
1. When would you use Redux and `this.setState({...})`?
Redux is needing to restore a specific piece of state - like the selected value in a dropdown on a page. Otherwise, setState will do just fine. 
1. What problem(s) does `Redux` solve?
The problem of state transfer between components. One-way data flow. 
1. What is the Context API?
It passes data through the component tree without having to pass props down manually at every level. 
## Vue.JS:

1. Name 2+ lifecycle methods?
1. Do components need templates?
1. What is `v-bind:` for?
1. How do you use props?
1. What are watches for?
1. What are computed methods?
1. Why/when should data be a function?
1. What is `v-model`? What does it affect?
1. How do you deploy/use `.vue` files?
1. How do you prevent default with an `v-on:click`/`@click=`?
1. Where should a component's logic/functions live?
1. What is reactivity in Vue?
1. Describe Vuex & and it's use case(s).
1. How is it similar to React? Different?


---------------

> Credit: Primary Source: Actual Interviews

