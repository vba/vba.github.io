## Stop use jQuery, you can do better without

_Wednesday, December 16th 2015_

### Preface

Probably you already heard such remarks before and probably you are fine with jQuery. So you are asking yourself, why there are crazy people who hate such awesome library and why should I stop use it. You'll be astonished to hear it but it's not about hate. Let's try to clarify the situation. 

As many of others I've started with jQuery in bronze age times (2007) when the gap between different browsers was so painful and the lack of common standards was so hateful. JQuery was a source of inspiration and a light ray in the time of darkness, it was revolutionary. I've fallen in love with jQuery when I've started use it. I wrote few handsome plugins with and I also organized few technical talks and team trainings around jQuery. But then, few years ago, I've changed my mind.

Let's see what's wrong with jQuery's usage in modern web development practices and how we could fix it.

#### Uniformization

One of the amazing killer-features of jQuery was an ability to smooth or fill the gap in the case of DOM usage under different browsers and theirs versions. Let's face the truth, a lot of things have changed since these times, especially the appearance of modern standards. Today in the most cases jQuery redirects the function's call to the standard DOM API, or exceptionally it can uses its own implementation of one or another feature. In the modern world we can easily survive without any usage of jQuery's selectors and utilities. We can simply replace following selectors:
```javascript
$('div, span, article');
$('#formId :invalid');
```
by:
```javascript
document.querySelectorAll('div, span, article');
document.querySelectorAll('#formId :invalid');
```
Or utilities like that:
```javascript
$.isArray(array1);
$.each(array, function(i, v) {
  // do something here
});
```
could be replaced by:
```javascript
Array.isArray(array1);
array1.forEach(function(v, i) {
  // do something here
}
```
Personally, I prefer always follow the standards, jQuery isn't one, it's just a library.

#### Wrapper object

As you probably know, after almost all of its manipulations, jQuery returns to you a specially object that wraps a result of its manipulations or the absence of such result. For example *$('span')* will return to you such object. It is not enough that the wrapper object has a plenty of its own, home-brewed methods, also those functions are roughly different from the modern web standards. Nothing guarantees you that such methods are homogeneous enough to use wrapper objects inside. Can you tell us about what will be referenced by *this* inside an event handler or what will be the first argument of such handler or even what value will have its special field *target*? Let's take a look to a small code sample:
```javascript
$('button').bind('click', function(e){
  var el = this; // Is it jQuery "object" or not ? Let's see the doc
  var event = e; // Is it jQuery "object" ? No, it's a special event-wrapper object
  var target = event.target; // Is it jQuery "object" ? Sure not, it's a simple DOM element
});
```
So buddies, sometimes we got a wrapper, sometimes not, but sometimes it could be a "special" wrapper, what a nonsense? Why should we complicate our live at this point?
You could suppose that there is a workaround, what about this silly naming convention to prefix all "special" objects with the dollar sign. Something like that:
```javascript
$('button').bind('click', function(e){
  var $el = $(this);
  var _event = e; // Let's use an another special convention for jQuery's events wrapper, prefix _
  var $event = e; // No, we should be coherent
  var target = $(event.target); // I'm sorry I forgot the dollar, because I'm just a human
  var target2 = $(target); // Oops, but I have to be sure that it's wrapped
  var var1 = someFunc(); // I forgot, this function should return $ or simple NodeList
  $(var1); // Never mind ...
});
```

#### jQuery as a perfect model of web development

How many times I heard such opinion that jQuery is a kind of perfect model for all possible types of web development. If you are web developer you have to use jQuery to achieve your goals and to aim the endless happiness. Probably because jQuery is good, it has balls, and it has a plenty of such awesome plugins. In my opinion it's a full bullshit, maybe it was partially true 5 years ago, but not now. It's the same thing as supposing that if you need to develop modern Windows 8/10 based applications you have to use pure Win32 API.

As I said above, jQuery it's just a library, taking in consideration present day trends, it's a low level library. Such stuff can not be suitable for writing wide, modern web applications. Nothing prevents you from usage of jQuery or pure DOM/API for realization of any kind of low-level task, but write with it an entire web application and then support it, is far to be a piece of cake. I saw a lot of different project becoming a huge plate of spaghetti on their client part, not because jQuery was a root of evil, just because it was too hard to manage tones of code and they ended up being overwhelmed.

How to avoid that? Use more appropriated/adapted solutions for your needs, solutions such as MV* frameworks/libraries for the complex web-application or something else for another needs.

#### Testing

This part is inextricable from previous one. As you know the human being is lazy, it's a nature, and good (automation)programmers are not an exception. Have you ever tested the code that rely on jQuery? Because of chaining methods it becomes non-trivial, tricky task. Especially if we take in consideration the fact that often the project based on pure jQuery can become fat incredibly fast and the developers have not time or cannot rearrange their code. The result is often oppressive. How you can speak about QA when even the author is unable to understand what his own code does.

If we talking about MV* approach, those problems can be simply avoided.

### Summary

If you were convinced by this article and you would like to try live and work without jQuery, you can check following links:

1. [You don't need jQuery](http://blog.garstasio.com/you-dont-need-jquery/) - Detailed blog about how to stop use jQuery
2. [Beyond jQuery](https://leanpub.com/beyondjquery) - The book about how to stop use jQuery
3. [The cost of frameworks](https://aerotwist.com/blog/the-cost-of-frameworks/) - Toughs about how expensive frameworks are and how developer can spare their time
4. [Zepto.js](http://zeptojs.com) - Small jQuery-compatible library, some kind of switch from hard drugs of jQuery to light cannabis Zepto.