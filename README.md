<!--
Creator: <Name>
Market: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# DOM Manipulation

### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

When you want to make changes happen on the page, you need to manipulate the DOM. jQuery as a tool is designed to simplify communication with the DOM.

### What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- describe and draw the document object model (DOM) of a simple HTML document.
- use the elements tab to view an manipulate the DOM and styling.
- explain the relationship between JavaScript and jQuery and the benefits of using jQuery for DOM manipulation
- select elements from the page using CSS Selectors and use jQuery to dynamically change the DOM

## DOM

The Document Object Model or DOM is a key concept to understanding what a browser does with your HTML. The browser looks at your HTML and creates a "tree", much like a family tree of siblings, parents, and children.

Draw the DOM tree for the following HTML

```html
  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
      <title></title>
    </head>
    <body>
      <p> This is an insightful paragraph </p>
      <ul>
        <li>item 1</li>
        <li>item 2</li>
      </ul>
    </body>
  </html>
```

## Intro to jQuery
jQuery is just JavaScript! It was invented in 2005 and has made our lives as developers better ever since.

We use jQuery because it's:

- Convenient: solves problems developers commonly face.
- Less Buggy: ensures javascript DOM manipulation works the same, cross-browser.
- Modern: brings javascript DOM manipulation into the 21st century.
- Popular: 15.3% of all sites and 70.4% of the top 100k sites use jQuery! (see Builtwith.com).

Sites like: css-tricks.com and jquery.com (!) include the jQuery library on their page. This means all you have to do is open up your Chrome Developer Console on one of those sites, and you can start playing with jQuery on the page!

#### How to get jQuery
You can only use jQuery if it's included in your page.

To do this, we have two options:

###### 1. Reference jQuery from a server on the internet:

  The quickest way to include jQuery in your project is to grab the jQuery library using a "CDN" (a blazing fast "content delivery network") and dropping it into a script tag in the head of your html (just google "jQuery cdn" and copy paste!):

  Any script tags for your own JavaScript files must come after the script tag for jQuery.


``` html
<!DOCTYPE html>
<html>
    <head>
        <script type="text/javascript" src="http://code.jquery.com/jquery-2.2.1.min.js"></script>
    </head>
    <body>
        <!-- Nothing here yet! -->
    </body>
</html>
```

###### 2. Download a copy of jQuery to host in your own project:

  [CDNJS](http://www.cdnjs.com), [Google Hosted Libraries](https://developers.google.com/speed/libraries/), and the [jQuery site](http://www.jquery.com) will all allow you to download a copy of jQuery to include in your projects. This means that the whole source code is in your project. If there are updates on that source code, you will need to make sure to update the version you have downloaded (kind of a pain).


#### Using jQuery
You know you're working with jQuery any time you see a `$()` in your code. `$` is an abbreviation for using the function name `jQuery` all over your code.

As you're working with jQuery to manipulate DOM elements, you are almost always either *getting* or *setting* a value. Memorize this pattern:  
- `$("CSS Selector").someJqueryMethodName()` - **getting** a value  
- `$("CSS Selector").someJqueryMethodName(setterValue)` - **setting** a value

For example, if you are viewing the home page on jQuery.com, then you can try the following in your Chrome Developer Console:  
- `$('p').text()` -- **get** the text of the readme (it lives inside of an `article` tag)  
- `$('p').text("Boo!")` -- **set** the text of the readme to "Boo!"

Wowza!
![wow](https://cloud.githubusercontent.com/assets/6520345/13719043/1bdbe8ce-e7a5-11e5-96ac-ea05ad01df88.gif)

Let's try another:  
- `$('p').css("background-color")` -- **get** the background color  
- `$('p').css("background-color", "orange")` -- **set** the background color to blue.

#### Documentation
Check out the `.text()` and `.css()` methods in the jQuery API Documentation: [text](http://api.jquery.com/text/), [css](http://api.jquery.com/css/).
- Pay close attention in the documentation: there's one section that talks about how to "get" text, and there's another section that talks about how to "set" text.
- `.text()` and `.css()` are not native javascript methods! They only work on jQuery-wrapped DOM Elements (that's what that `$` is doing).

For more cool DOM manipulation tricks, you'll need to hit the docs:
- jQuery API [Documentation](jquery.com)
    - [Manipulation Methods](http://api.jquery.com/category/manipulation/)
    - [DOM Tree Traversal Methods](http://api.jquery.com/category/traversing/)

The more you struggle with this kind of documentation, the stronger your coding-chops will become!


#### jQuery is just Javascript
Everything you do in jQuery can be done in pure/vanilla javascript.

Take a look at the [raw jquery library](http://code.jquery.com/jquery-2.1.3.js) (it's just a bunch of javascript!).

jQuery often saves *you* a bunch of time. Because it's just JavaScript under the hood, some argue [you might not need jQuery](http://youmightnotneedjquery.com). It's always less efficient for the computer to execute jQuery (this often doesn't matter though) and it sometimes can be overkill, depending on what you're doing.

Take a look at [this Comparison of jQuery and Vanilla JS](http://bl.ocks.org/joyrexus/7307312) . Here are some of the basic differences:



**Selecting Elements**

Note: the jQuery variables below are named with `$` at the beginning in order to indicate that they're jQuery created objects. This is a convention, not required syntax.
```js
// jquery
var $divs = $('div');

// vanilla js
var divs = document.querySelectorAll('div');
```

**Selecting Elements by Class**

```js
// jquery
var $content = $('.content');

// vanilla js
var content = document.getElementsByClassName('content');
```

**Selecting Elements by Id**

```js
// jquery
var $about = $('#about');

// vanilla js
var about = document.getElementById('about');
```

**Creating Elements**

```js
// jquery
var $newDiv = $('<div></div>');
$('body').append($newDiv);

// vanilla js
var newDiv = document.createElement('div');
document.body.appendChild(newDiv);
```
