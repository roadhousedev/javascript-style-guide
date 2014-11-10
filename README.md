Roadhosue Digital Javascript style guide
======================

Based off of [AirBnB's style guide](https://github.com/airbnb/javascript).

*Keeping our JavaScript more consistent*

## Table of Contents

  1. [Strings](#strings)
  1. [Variables](#variables)
  1. [Semicolons](#semicolons)
  1. [Commas](#commas)
  1. [Declaring Strict Mode](#declaring-strict-mode)
  1. [Naming Conventions](#naming-conventions)
  1. [Conditional Expressions](#conditional-expressions)
  1. [Blocks](#blocks)
  1. [Comments](#comments)
  1. [Spacing](#spacing)
  1. [Types](#types)
  1. [Objects](#objects)
  1. [Arrays](#arrays)
  1. [Properties](#properties)
  1. [Accessors](#accessors)
  1. [jQuery](#jquery)
  1. [Tools](#tools)
  1. [License](#license)

## Strings

Use single quotes `''` for strings instead of double quotes `""`

  ```javascript
  // bad
  var name = "Roadhouse Digital";

  var fullName = "Roadhouse " + this.lastName;

  // good
  var name = 'Roadhouse Digital';

  var fullName = 'Roadhouse ' + this.lastName;
  ```

**[⬆ back to top](#table-of-contents)**


## Variables

Declarations for `var` as follows:

  ```javascript
  // bad
  var a = 1;
  var b = 2;
  var c = 'string';

  // good
  var a = 1,
   b = 2,
   c = 'string';
  ```
**[⬆ back to top](#table-of-contents)**


## Semicolons

Use semicolons `;`

  ```javascript
  // bad
  function() {
    return 'Roadhouse'
  }

  // good
  function() {
    return 'Roadhouse';
  }
  ```

**[⬆ back to top](#table-of-contents)**

## Commas

Don't use leading commas.

  ```javascript
  // bad
  var roadhouse
    , digital
    , data;

  // good
  var roadhouse,
      digital,
      data;

  // bad
  var product = {
      name: 'Roadhouse'
    , type: 'Company'
    , category: 'Development'
  };

  // good
  var product = {
    name: 'Roadhouse',
    type: 'Company',
    category: 'Development'
  };

  // good
  function() {
    return 'Roadhouse';
  }
  ```

**[⬆ back to top](#table-of-contents)**

## Naming conventions

  - Use descriptive naming. Avoid single letter names.

  ```javascript
  // bad
  function t() {
    // do something...
  }

  // good
  function test() {
    // do something...
  }
  ```

  - Use camelCase when naming objects, functions, and instances.

  ```javascript
  // bad
  var OBject = {};
  var heres_an_object = {};
  function c() {}
  var u = new user({
    name: 'Roadhouse';
  });

  // good
  var thisIsMyObject = {};
  function thisIsMyFunction() {}
  var user = new User({
    name: 'Roadhouse';
  });
  ```

**[⬆ back to top](#table-of-contents)**


## Declaring Strict Mode

Declare `'use strict'` in all your JavaScript files.


**[⬆ back to top](#table-of-contents)**

##Conditional Expressions

Use `===` and `!==`

```javascript
  // bad
  var name = 'Road house';
  if(name == 'Road house'){}

  if(name != 'Road house'){}

  // good
  var name = 'Road house';
  if(name === 'Road house'){}

  if(name !== 'Road house'){}
  ```
**[⬆ back to top](#table-of-contents)**


##Blocks

Use braces when there are multi-line blocks.

```javascript
  // bad
  if (name)
  return false;

  // good
  if (name) return false;

  // bad
  if (name){return false};

  // good
  if (name){
    return false;
  }
  ```
**[⬆ back to top](#table-of-contents)**


## Comments

  - Use `/** ... */` for multiline comments. Include a description, specify types and values for all parameters and return values.

    ```javascript
    // bad
    // make() returns a new element
    // based on the passed in tag name
    //
    // @param <String> tag
    // @return <Element> element
    function make(tag) {

      // ...stuff...

      return element;
    }

    // good
    /**
     * make() returns a new element
     * based on the passed in tag name
     *
     * @param <String> tag
     * @return <Element> element
     */
    function make(tag) {

      // ...stuff...

      return element;
    }
    ```

  - Use `//` for single line comments. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment.

    ```javascript
    // bad
    var active = true;  // is current tab

    // good
    // is current tab
    var active = true;

    // bad
    function getType() {
      console.log('fetching type...');
      // set the default type to 'no type'
      var type = this._type || 'no type';

      return type;
    }

    // good
    function getType() {
      console.log('fetching type...');

      // set the default type to 'no type'
      var type = this._type || 'no type';

      return type;
    }
    ```

  - Prefixing your comments with `FIXME` or `TODO` helps other developers quickly understand if you're pointing out a problem that needs to be revisited, or if you're suggesting a solution to the problem that needs to be implemented. These are different than regular comments because they are actionable. The actions are `FIXME -- need to figure this out` or `TODO -- need to implement`.

  - Use `// FIXME:` to annotate problems

    ```javascript
    function Calculator() {

      // FIXME: shouldn't use a global here
      total = 0;

      return this;
    }
    ```

  - Use `// TODO:` to annotate solutions to problems

    ```javascript
    function Calculator() {

      // TODO: total should be configurable by an options param
      this.total = 0;

      return this;
    }
  ```

**[⬆ back to top](#table-of-contents)**


## Whitespace

  - Use soft tabs set to 2 spaces

    ```javascript
    // bad
    function() {
    ∙∙∙∙var name;
    }

    // bad
    function() {
    ∙var name;
    }

    // good
    function() {
    ∙∙var name;
    }
    ```

  - Place 1 space before the leading brace.

    ```javascript
    // bad
    function test(){
      console.log('test');
    }

    // good
    function test() {
      console.log('test');
    }

    // bad
    dog.set('attr',{
      age: '1 year',
      breed: 'Bernese Mountain Dog'
    });

    // good
    dog.set('attr', {
      age: '1 year',
      breed: 'Bernese Mountain Dog'
    });
    ```

  - Set off operators with spaces.

    ```javascript
    // bad
    var x=y+5;

    // good
    var x = y + 5;
    ```

  - End files with a single newline character.

    ```javascript
    // bad
    (function(global) {
      // ...stuff...
    })(this);
    ```

    ```javascript
    // bad
    (function(global) {
      // ...stuff...
    })(this);↵
    ↵
    ```

    ```javascript
    // good
    (function(global) {
      // ...stuff...
    })(this);↵
    ```

  - Use indentation when making long method chains.

    ```javascript
    // bad
    $('#items').find('.selected').highlight().end().find('.open').updateCount();

    // good
    $('#items')
      .find('.selected')
        .highlight()
        .end()
      .find('.open')
        .updateCount();

    // bad
    var leds = stage.selectAll('.led').data(data).enter().append('svg:svg').class('led', true)
        .attr('width',  (radius + margin) * 2).append('svg:g')
        .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
        .call(tron.led);

    // good
    var leds = stage.selectAll('.led')
        .data(data)
      .enter().append('svg:svg')
        .class('led', true)
        .attr('width',  (radius + margin) * 2)
      .append('svg:g')
        .attr('transform', 'translate(' + (radius + margin) + ',' + (radius + margin) + ')')
        .call(tron.led);
    ```

**[⬆ back to top](#table-of-contents)**

## Types

  - **Primitives**: When you access a primitive type you work directly on its value

    + `string`
    + `number`
    + `boolean`
    + `null`
    + `undefined`

    ```javascript
    var foo = 1,
        bar = foo;

    bar = 9;

    console.log(foo, bar); // => 1, 9
    ```
  - **Complex**: When you access a complex type you work on a reference to its value

    + `object`
    + `array`
    + `function`

    ```javascript
    var foo = [1, 2],
        bar = foo;

    bar[0] = 9;

    console.log(foo[0], bar[0]); // => 9, 9
    ```

**[⬆ back to top](#table-of-contents)**

## Objects

  - Use the literal syntax for object creation.

    ```javascript
    // bad
    var item = new Object();

    // good
    var item = {};
    ```

  - Don't use [reserved words](http://es5.github.io/#x7.6.1) as keys. It won't work in IE8.

    ```javascript
    // bad
    var superman = {
      default: { clark: 'kent' },
      private: true
    };

    // good
    var superman = {
      defaults: { clark: 'kent' },
      hidden: true
    };
    ```

  - Use readable synonyms in place of reserved words.

    ```javascript
    // bad
    var superman = {
      class: 'alien'
    };

    // bad
    var superman = {
      klass: 'alien'
    };

    // good
    var superman = {
      type: 'alien'
    };
    ```

**[⬆ back to top](#table-of-contents)**

## Arrays

  - Use the literal syntax for array creation

    ```javascript
    // bad
    var items = new Array();

    // good
    var items = [];
    ```

  - If you don't know array length use Array#push.

    ```javascript
    var someStack = [];


    // bad
    someStack[someStack.length] = 'abracadabra';

    // good
    someStack.push('abracadabra');
    ```

  - When you need to copy an array use Array#slice. [jsPerf](http://jsperf.com/converting-arguments-to-an-array/7)

    ```javascript
    var len = items.length,
        itemsCopy = [],
        i;

    // bad
    for (i = 0; i < len; i++) {
      itemsCopy[i] = items[i];
    }

    // good
    itemsCopy = items.slice();
    ```

  - To convert an array-like object to an array, use Array#slice.

    ```javascript
    function trigger() {
      var args = Array.prototype.slice.call(arguments);
      ...
    }
    ```

**[⬆ back to top](#table-of-contents)**


## Properties

  - Use dot notation when accessing properties.

    ```javascript
    var roadhouse = {
      elephant: true,
      remember: true
    };

    // bad
    var isElephant = roadhouse['elephant'];

    // good
    var isElephant = roadhouse.elephant;
    ```

  - Use subscript notation `[]` when accessing properties with a variable.

    ```javascript
    var roadhouse = {
      elephant: true,
      remember: true
    };

    function getProp(prop) {
      return evernote[prop];
    }

    var isElephant = getProp('elephant');
    ```

**[⬆ back to top](#table-of-contents)**

## Accessors

  - Accessor functions for properties are not required
  - If you do make accessor functions use getVal() and setVal('hello')

    ```javascript
    // bad
    elephant.age();

    // good
    elephant.getAge();

    // bad
    elephant.age(25);

    // good
    elephant.setAge(25);
    ```

  - If the property is a boolean, use isVal() or hasVal()

    ```javascript
    // bad
    if (!elephant.age()) {
      return false;
    }

    // good
    if (!elephant.hasAge()) {
      return false;
    }
    ```

**[⬆ back to top](#table-of-contents)**

## jQuery

  - Prefix jQuery object variables with a `$`.

    ```javascript
    // bad
    var sidebar = $('.sidebar');

    // good
    var $sidebar = $('.sidebar');
    ```

  - Cache jQuery lookups.

    ```javascript
    // bad
    function setSidebar() {
      $('.sidebar').hide();

      // ...stuff...

      $('.sidebar').css({
        'background-color': 'pink'
      });
    }

    // good
    function setSidebar() {
      var $sidebar = $('.sidebar');
      $sidebar.hide();

      // ...stuff...

      $sidebar.css({
        'background-color': 'pink'
      });
    }
    ```

  - For DOM queries use Cascading `$('.sidebar ul')` or parent > child `$('.sidebar > ul')`. [jsPerf](http://jsperf.com/jquery-find-vs-context-sel/16)
  - Use `find` with scoped jQuery object queries.

    ```javascript
    // bad
    $('ul', '.sidebar').hide();

    // bad
    $('.sidebar').find('ul').hide();

    // good
    $('.sidebar ul').hide();

    // good
    $('.sidebar > ul').hide();

    // good
    $sidebar.find('ul').hide();
    ```

**[⬆ back to top](#table-of-contents)**



## Tools

#### Grunt
  - [JSHint](https://github.com/gruntjs/grunt-contrib-jshint)

**[⬆ back to top](#table-of-contents)**

## License

(The MIT License)

Copyright (c) 2014 Airbnb

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

**[⬆ back to top](#table-of-contents)**

# };
