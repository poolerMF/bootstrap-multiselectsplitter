# bootstrap-multiselectsplitter

Transforms a &lt;select&gt; containing one or more &lt;optgroup&gt; in two chained &lt;select&gt;.

This script is better version of [bootstrap-selectsplitter](https://github.com/xavierfaucon/bootstrap-selectsplitter), for multi select with more script options.
If you want to select more options, you must hold CTRL key. (default select behaviour)

This:

![image1](http://img4.hostingpics.net/pics/927121bootstrapselectsplitterimage1.png)

Becomes this:

![image2](http://img4.hostingpics.net/pics/997752bootstrapselectsplitterimage2.png)


## Dependencies
- boostrap CSS > 3.0
- jquery > 1.9.1
```HTML
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap.min.css">
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
```

## Installation

```
bower install bootstrap-multiselectsplitter
```


## Usage

Create a &lt;select&gt; with at least one &lt;optgroup&gt;.

Each &lt;option&gt; of your &lt;select&gt; must have a unique value.

```HTML
<select multiple="multiple">
  <optgroup label="Category 1">
    <option value="1">Choice 1</option>
    <option value="2">Choice 2</option>
    <option value="3">Choice 3</option>
    <option value="4">Choice 4</option>
  </optgroup>
  <optgroup label="Category 2">
    <option value="5">Choice 5</option>
    <option value="6">Choice 6</option>
    <option value="7">Choice 7</option>
    <option value="8">Choice 8</option>
  </optgroup>
  <optgroup label="Category 3">
    <option value="9">Choice 9</option>
    <option value="10">Choice 10</option>
    <option value="11">Choice 11</option>
    <option value="12">Choice 12</option>
  </optgroup>
</select>
```
```JavaScript
$('select').multiselectsplitter();
```

## Examples

[Online demo](https://jsfiddle.net/j4vprjsg/)


## Options
* **selectSize** - define size of new selects ... when null, automatically setted by longest option count `DEFAULT: null`
* **maxSelectSize** - define max size of new selects `DEFAULT: null`
* **clearOnFirstChange** - when true, second select will be cleared when the first changes `DEFAULT: false`
* **onlySameGroup** - when true, only options from one optGroup can be selected (option works only for multiselect) `DEFAULT: false`
* **groupCounter** - when true, there will be added counter of how many options are selected  (option works only for multiselect) `DEFAULT: false`
* **maximumSelected** - define how many options can be selected. Can be integer or function with arguments ($firstSelect, $secondSelect) that return integer. (option works only for multiselect) `DEFAULT: null`
* **afterInitialize** - function with 2 arguments ($firstSelect, $secondSelect) - called after initialization `DEFAULT: null`
* **maximumAlert** - function called when selected more than '**maximumSelected**' options ... `DEFAULT: function (maximumSelected) { alert("Only " + maximumSelected + " values can be selected"); }`
* **createFirstSelect** - function for creating option in first select `DEFAULT: function (label, $originalSelect) { return '<option>' + label + '</option>'; }`
* **createSecondSelect** - function for creating option in second select `DEFAULT: function (label, $firstSelect) { return '<option>' + label + '</option>'; }`
* **template** - template for new selects `DEFAULT: <div class="row" data-multiselectsplitter-wrapper-selector><div class="col-xs-12 col-sm-6"><select class="form-control" data-multiselectsplitter-firstselect-selector></select></div><div class="col-xs-12 col-sm-6"><select class="form-control" data-multiselectsplitter-secondselect-selector></select></div></div>`

## Copyright and license

Copyright (C) 2016 Ing. Matúš Ferko

Licensed under the MIT license.