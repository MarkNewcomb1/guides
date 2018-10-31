# Tech Screen Interview Questions

## CSS

1. What are CSS selectors?

_Just points to the element(s) you want to style. A selector has a property and a value._

1. What is selector specificity?

_It decides which selector "wins" when there's conflicting css rules pointing to the same element. An html tag selector has a specificity of 1, a class has 10, an id has 100, and inline styling has 1,000._

1. What is the difference between selectors `.class1.class2` and `.class1 .class2` (space added)?

_The first one selects an element with both class1 and class2 on it. The second one is a descendant selector, which selects an element with a class of class2 that's inside an element with a class of class1._

1. How about these selectors `.class1 .class2` and `.class1 > .class2`?

_The first one is a descendant selector - selects an element of class2 that's inside class1, but the second one is a child selector, which only selects immediate children of it. Used a lot with uls and lis._
1. And these selectors `.header .nav a` and `.header a`?

_It's the same concept of descendant selectors, but the first one is three levels deep, and the second is only two._

1. How do you center something in CSS?

_The tried-and-true trick for me is `display: block; margin: 0 auto;`. For flexbox, though, on its parent container, you use `display: flex; align-items: center; justify-content: center;`._

1. What is SASS/LESS/Stylus/etc?

_SASS stands for Syntactically Awesome Stylesheets, and it's a language for stylesheets that's a preprocessor scripting language. It requires a compilier to "translate" SASS into CSS a browser can read, but it gives you additional functionality like storing variables, nesting selectors, etc._ 

1. What is component based SCSS/CSS? 

_It writes CSS rules in ES6 with `const` and backticks._

1. ~~How do floats work?~~
1. How do you get something to not display using CSS?

_`display: none;`, although if you want it to still take up the space on the page as if it were visible, then `opacity: 0;`_

1. Why would you use Flexbox or CSS Grid?

_Flexbox is either rows or columns. Grid is generally for both._ 

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

_Immediately invoked function expression. It runs as soon as it's defined. Example:_
```javascript 
(function () {
    statements
})();
```


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

_Babel's a JavaScript compilier. You need a way to translate React's JSX syntax into vanilla JavaScript to run in web browsers._

1. When would you use Redux and `this.setState({...})`?
Redux is needing to restore a specific piece of state - like the selected value in a dropdown on a page. Otherwise, setState will do just fine. 
1. What problem(s) does `Redux` solve?
The problem of state transfer between components. One-way data flow. 
1. What is the Context API?
It passes data through the component tree without having to pass props down manually at every level. 
## Vue.JS:

1. Name 2+ lifecycle methods?

_mounted, gives access to templates and enables interaction with the DOM. beforeUpdate, runs after data changes on the component and the update cycle begins right before the DOM is patches and re-rendered. Useful for debugging._

1. Do components need templates?

_No - you can create what's called a renderless component that only manages state and behavior._

1. What is `v-bind:` for?

_It's a directive which are like HTML attributes. For, say, the href attribute of an a tag, you have to use v-bind:_

```
<a v-bind:href="url">{{ linkText }}</a>
```
_It's so common that there's a shorthand for it:_


```
<a :href="url">{{ linkText }}</a>
```

1. How do you use props?

_You have to register them in your component, and then you pass data to it as a custom attribute. It's a way to pass data to child components._

1. What are watches for?

_They're for executing logic that applies to something else when a change on a property occurs. So if you have an input type number that allows you to uptick and downtick a number in a box, that component's data can be 0 to begin with, but you can make a watch() function watch for the change to this number and do something else, like console.log "The counter has changed!"_

1. What are computed methods?

_I did not see computed method anywhere in the Vue docs. Computed properties, however, are cached based on their dependencies. If it's not a reactive dependency, then it won't ever update, like the following computed property:_

```javascript
computed: {
  now: function () {
    return Date.now()
  }
}
```
1. Why/when should data be a function?

_The official docs state that a component's data option MUST be a function, so that each instance can maintain their independent copy of the return data object. Here's an example of one:_

```javascript
data: function () {
  return {
    count: 0
  }
}
```

1. What is `v-model`? What does it affect?

_Like v-bind, it's also a directive. But v-model is two-way data binding. So on a form, you can bind the input element and have that change some Vue data property elsewhere:_

```
<input v-model="message" placeholder="Enter a message">
<p>Message is: {{ message }}</p>
```


1. How do you deploy/use `.vue` files?
1. How do you prevent default with an `v-on:click`/`@click=`?

_Vue has event modifiers for this for v-on. For a form:_

```
<!-- the submit event will no longer reload the page -->
<form v-on:submit.prevent="onSubmit"></form>
```

_For v-on:click_

```
v-on:click.prevent.self will prevent all clicks while v-on:click.self.prevent will only prevent clicks on the element itself.
```

1. Where should a component's logic/functions live?

_Inside the script tag; specifically, the method object._


1. What is reactivity in Vue?

_It's how Vue tracks changes in ways that procedural JavaScript does not. When you pass an object to Vue as its data option, Vue will walk through the properties and convert them to getters and setters using Object.defineProperty._

1. Describe Vuex & and it's use case(s).

_If you need the same data at two completely different places in your application. Or to persist state, like an application to still work even if the user is offline. If you have a to-do app, for example, and you want to fetch all the items from an API on one page but also have pages to display only certain categories of to-do items. Those are two places in the app that need to look at the same chunk of data._

1. How is it similar to React? Different?

_It's a front-end framework that's gotten popular recently, with it's seperation of concerns. However, with Vue (and also Angular which it came from) you get directives like v-for (from ngFor), whereas React uses .map instead._

---------------

> Credit: Primary Source: Actual Interviews

