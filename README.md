# showcar-ui

This module provides several predefined classes, scss mixins and variables for simple page styling with the showcar ui library

## Installation:

To install showcar-ui within your project use bower.

    bower install --save git@github.com:AutoScout24/showcar-ui.git


## How to include:
To make the ShowCar-UI Library available within you frontend, it is necessary to include some javascript and (s)css

### Simple Include

The simple include only needs some additions in your html code:

#### CSS

    <link href="./src/lib/showcar-ui/dist/showcar-ui.css" ... >
    
#### CSS (Namespaced version)

If you want to use the showcar ui styling only in a certain part of your application, you can use the namespaced version.
Therefor you have to include the namespaced version of the css and add the data-showcar-ui attribute to the element you want to apply the styles to.

    <link href="./src/lib/showcar-ui/dist/showcar-ui-namespaced.css" ... >
    
    <body data-showcar-ui>

#### JavaScript

You only need to include one JavaScript file. It enables all supported elements by default and exports some global variables, such as Storage.

    <script async src="./src/lib/showcar-ui/dist/showcar-ui.min.js"></script>


### Advanced Include

The advanced include needs some changes in your main scss file:

#### CSS

    @import "../lib/showcar-ui/src/scss/showcar-ui";
    
With this method, you can use all the mixins defined in the library within your own scss code.
    
## Additional information

The showcar-ui library includes some other libraries:

* showcar-storage
* showcar-icons
* Zepto

### showcar-storage

You can access the Stroage API via the global `Storage` object. For further information see the documentation under https://github.com/AutoScout24/showcar-storage

### showcar-icons

You can use all the icons defined by showcar-icons with the custom `<as24-icon>` tag. For further information see the documentation under https://github.com/AutoScout24/showcar-icons

### Zepto

Showcar-ui includes Zepto, which is a lightweight replacement for jQuery. You can access Zepto via the global variables `$` and `Zepto`. 
For a detailed usage guide, have a look at http://zeptojs.com/ 

## How to use:

for the use of the library have a look at the documentation that is located in the docs directory.

## How to contribute:

TBD

## License

MIT License


    <link rel="stylesheet" href="dist/showcar-ui.css">
    <link rel="stylesheet" href="docs/css/highlight.css">
    <link rel="stylesheet" href="docs/css/documenation.css">

    <script src="js/highlight.pack.js"></script>
    <script>hljs.initHighlightingOnLoad();</script>
    <script>
        SURROGATE_PAIR_REGEXP = /[\uD800-\uDBFF][\uDC00-\uDFFF]/g;
        NON_ALPHANUMERIC_REGEXP = /([^\#-~| |!])/g;

        function encodeEntities(value) {
            return value.
                    replace(/&/g, '&amp;').
                    replace(SURROGATE_PAIR_REGEXP, function(value) {
                        var hi = value.charCodeAt(0);
                        var low = value.charCodeAt(1);
                        return '&#' + (((hi - 0xD800) * 0x400) + (low - 0xDC00) + 0x10000) + ';';
                    }).
                    replace(NON_ALPHANUMERIC_REGEXP, function(value) {
                        return '&#' + value.charCodeAt(0) + ';';
                    }).
                    replace(/</g, '&lt;').
                    replace(/>/g, '&gt;');
        }
        function formatCode (code, target) {
            document.querySelector(target).innerHTML = encodeEntities(code);
        }
    </script>
<h1>ShowCar UI Library Docs</h1>

<ul class="docs-navigation">
    <li><a href="#content-container">Content container</a></li>
    <li><a href="#grid">Grid</a></li>
    <li><a href="#buttons">Buttons</a></li>
    <li>
        <a href="#typography">Typography</a>
        <ul>
            <li><a href="#body-copy">Body copy</a></li>
            <li><a href="#links">Links</a></li>
        </ul>
    </li>
    <li>
        <a href="#forms">Forms</a>
        <ul>
            <li><a href="#inputs-textareas">Inputs</a></li>
            <li><a href="#selects">Select Boxes</a></li>
            <li><a href="#radios">Radio Buttons</a></li>
            <li><a href="#checkboxes">Checkboxes</a></li>
            <li><a href="#color-selector">Color Selectors</a></li>
            <li><a href="#input-groups">Input Groups</a></li>
        </ul>
    </li>
    <li>
        <a href="#helper">Helper classes</a>
        <ul>
            <li><a href="#floats">floats</a></li>
            <li><a href="#text-alignment">Text alignment</a></li>
            <li><a href="#center-blocks">Center content blocks</a></li>
            <li><a href="#horizontal-line">Horizontal line</a></li>
        </ul>
    </li>
    <li>
        <a href="#components">Components</a>
        <ul>
            <li><a href="#collapse">Collapse</a></li>
        </ul>
    </li>
</ul>

<hr>
<div>
    <a name="content-container"></a>
    <h2>Content container</h2>

    <p>The content container is a responsive element containing the entire content section. It takes care of the proper positioning of the content.</p>

    <div class="example example-content-container">
        <div class="content-container">Your Content goes here</div>
        <div class="clearfix"></div>
    </div>
    <pre><code class="html" id="code-content-container"></code></pre>
    <script>
        formatCode(`<div class="content-container">...</div>`, '#code-content-container');
    </script>

</div>
<div>
    <a name="grid"></a>
    <h2>Grid</h2>
    <p>ShowCar UI includes the responsive <a href="http://susydocs.oddbird.net" target="_blank">Susy</a> grid system. It is implemented with a 12 column layout. There are predefined classes for grid rows and grid columns.</p>
    <p>Every grid row has to be placed within a <code>.grid-row</code> container. Every grid cell is a <code>.grid-col-*</code> container.</p>

    <div class="example example-grid">
        <div class="grid-row">
            <div class="grid-col-12">
                .grid-col-12
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-6">
                .grid-col-6
            </div>
            <div class="grid-col-6">
                .grid-col-6
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-4">
                .grid-col-4
            </div>
            <div class="grid-col-4">
                .grid-col-4
            </div>
            <div class="grid-col-4">
                .grid-col-4
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-3">
                .grid-col-3
            </div>
            <div class="grid-col-3">
                .grid-col-3
            </div>
            <div class="grid-col-3">
                .grid-col-3
            </div>
            <div class="grid-col-3">
                .grid-col-3
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-2">
                .grid-col-2
            </div>
            <div class="grid-col-2">
                .grid-col-2
            </div>
            <div class="grid-col-2">
                .grid-col-2
            </div>
            <div class="grid-col-2">
                .grid-col-2
            </div>
            <div class="grid-col-2">
                .grid-col-2
            </div>
            <div class="grid-col-2">
                .grid-col-2
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
            <div class="grid-col-1">
                .grid-col-1
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-8">
                .grid-col-8
            </div>
            <div class="grid-col-4">
                .grid-col-4
            </div>
        </div>
        <div class="grid-row">
            <div class="grid-col-3">
                .grid-col-3
            </div>
            <div class="grid-col-6">
                .grid-col-6
            </div>
            <div class="grid-col-3">
                .grid-col-3
            </div>
        </div>
    </div>
    <pre><code class="html" id="code-grid"></code></pre>
    <script>
        formatCode(`<div class="grid-row">
    <div class="grid-col-6">.grid-col-6</div>
    <div class="grid-col-6">.grid-col-6</div>
</div>
<div class="grid-row">
    <div class="grid-col-3">.grid-col-3</div>
    <div class="grid-col-3">.grid-col-3</div>
    <div class="grid-col-3">.grid-col-3</div>
    <div class="grid-col-3">.grid-col-3</div>
</div>`, '#code-grid');
    </script>
</div>

<div>
    <a name="buttons"></a>
    <h2>Buttons</h2>
    <p>ShowCar uses two types of buttons <code>.btn-bob-&lt;size&gt;</code> and <code>.btn-ross-&lt;size&gt;</code> in two different sizes (<code>l</code>and <code>m</code>)</p>
    <p>Use the button classes on an <code>&lt;a&gt;</code>, <code>&lt;button&gt;</code>, or <code>&lt;input&gt;</code> element</p>
    <p><code>.btn-block</code> adds block style to a button, which stretches the button to full width.</p>

    <div class="example example-buttons">
        <div>
            <button class="btn-bob-m">.btn-bob-m</button>
            <button class="btn-ross-m">.btn-ross-m</button>
        </div>
        <div>
            <button class="btn-bob-l">.btn-bob-l</button>
            <button class="btn-ross-l">.btn-ross-l</button>
        </div>
        <div>
            <button class="btn-bob-m" disabled>disabled</button>
            <button class="btn-ross-m" disabled>disabled</button>
        </div>
        <div>
            <button class="btn-bob-m btn-block">.btn-bob-m.btn-block</button>
            <button class="btn-ross-l btn-block">.btn-ross-l.btn-block</button>
        </div>
    </div>
    <pre><code class="html" id="code-buttons"></code></pre>
    <script>
        formatCode(`<button class="btn-bob-m">.btn-bob-m</button>
<button class="btn-ross-m">.btn-ross-m</button>
<button class="btn-bob-l">.btn-bob-l</button>
<button class="btn-ross-l">.btn-ross-l</button>
<button class="btn-bob-m" disabled>disabled</button>
<button class="btn-ross-m" disabled>disabled</button>
<button class="btn-bob-m btn-block">.btn-bob-m.btn-block</button>
<button class="btn-ross-l btn-block">.btn-ross-l.btn-block</button>`, '#code-buttons');
    </script>
</div>

<div>
    <a name="typography"></a>
    <h2>Typography</h2>
    <a name="body-copy"></a>
    <h3>Body copy</h3>
    <p>
        ShowCars default <code>font-family</code> is <span class="font-bold">Source Sans Pro</span>. Please use the predefined classes to increase or decrease the font size. You should not define explicit font sizes.
    </p>
    <div class="example example-body-copy">
        <p class="font-m">.font-m (default)<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-s">.font-s<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-l">.font-l<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-xl">.font-xl<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-xxl">.font-xxl<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-xxxl">.font-xxxl<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>

        <p class="font-silent">.font-silent<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
        <p class="font-bold">.font-bold<br />Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>
    </div>
    <pre><code class="html" id="code-typography"></code></pre>
    <script>
        formatCode(`<p class="font-m">...</p>
<p class="font-s">...</p>
<p class="font-l">...</p>
<p class="font-xl">...</p>
<p class="font-silent">...</p>
<p class="font-bold">...</p>
        `, '#code-typography');
    </script>

    <a name="links"></a>
    <h3>Links</h3>
    <div class="example example-links">
        <div>
            <a>Default Link</a>
        </div>
        <div>
            <a class="inline-link">Inline Link</a>
        </div>
    </div>
    <pre><code class="html" id="code-links"></code></pre>
    <script>
        formatCode(`<a href="...">...</a>
<a href="..." class="inline-link">...</a>`,'#code-links');
    </script>
</div>
<div>
    <a name="forms"></a>
    <h2>Forms</h2>
    <a name="inputs-textareas"></a>
    <h3>Inputs / Textareas</h3>

    <div class="example example-inputs">
        <input type="text" placeholder="default (.input-m)">
        <input type="text" placeholder=".input-l" class="input-l">

        <input type="text" placeholder="disabled" disabled>
        <input type="text" placeholder=".info" class="info">
        <input type="text" placeholder=".success" class="success">
        <input type="text" placeholder=".error" class="error">

        <textarea readonly>textarea</textarea>
    </div>
    <pre><code class="html" id="code-inputs"></code></pre>
    <script>
        formatCode(`<input type="text">
<input type="text" class="input-l">
<input type="text" disabled>
<input type="text" class="info">
<input type="text" class="success">
<input type="text" class="error">
<textarea>...</textarea>`, '#code-inputs');
    </script>

    <a name="selects"></a>
    <h3>Select Boxes</h3>
    <div class="example example-selects">
        <select name="as24-select-1">
            <option>default (.input-m)</option>
            <option>Option 2</option>
            <option>Option 3</option>
        </select>
        <select name="as24-select-2" class="input-l">
            <option>.input-l</option>
            <option>Option 2</option>
            <option>Option 3</option>
        </select>
        <select name="as24-select-3" class="input-l" disabled>
            <option>disabled</option>
        </select>
    </div>
    <pre><code class="html" id="code-selects"></code></pre>
    <script>
        formatCode(`<select>
    <option>...</option>
</select>

<select class="input-l">
    ...
</select>

<select class="input-l" disabled>
    ...
</select>`, '#code-selects');
    </script>

    <a name="radios"></a>
    <h3>Radio Buttons</h3>
    <div class="example example-radios">
        <div>
            <input id="as24-radio-1" type="radio" name="example-radios-1">
            <label for="as24-radio-1">Radio 1</label>

            <input id="as24-radio-2" type="radio" name="example-radios-1">
            <label for="as24-radio-2">Radio 2</label>

            <input id="as24-radio-3" type="radio" disabled name="example-radios-1">
            <label for="as24-radio-3">Radio 3 (disabled)</label>
        </div>
        <div>
            <input id="as24-radio-4" class="input-l" type="radio" name="example-radios-2">
            <label for="as24-radio-4">Radio 1</label>

            <input id="as24-radio-5" class="input-l" type="radio" name="example-radios-2">
            <label for="as24-radio-5">Radio 2</label>

            <input id="as24-radio-6" class="input-l" type="radio" disabled name="example-radios-2">
            <label for="as24-radio-6">Radio 3 (disabled)</label>
        </div>
    </div>
    <pre><code class="html" id="code-radios"></code></pre>
    <script>
        formatCode(`<input id="radio1" type="radio">
<label for="radio1">...</label>

<input id="radio2" type="radio" disabled>
<label for="radio2">...</label>`, '#code-radios');
    </script>

    <a name="checkboxes"></a>
    <h3>Checkboxes</h3>
    <div class="example example-checkboxes">
        <div>
            <input id="as24-checkbox-1" type="checkbox">
            <label for="as24-checkbox-1">Checkbox</label>

            <input id="as24-checkbox-2" type="checkbox" disabled>
            <label for="as24-checkbox-2">Checkbox (disabled)</label>
        </div>
        <div>
            <input id="as24-checkbox-3" type="checkbox" class="input-l">
            <label for="as24-checkbox-3">Checkbox</label>

            <input id="as24-checkbox-4" type="checkbox" disabled class="input-l">
            <label for="as24-checkbox-4">Checkbox (disabled)</label>
        </div>
    </div>
    <pre><code class="html" id="code-checkboxes"></code></pre>
    <script>
        formatCode(`<input id="cb1" type="checkbox">
<label for="cb1">...</label>

<input id="cb2" type="checkbox" disabled>
<label for="cb2">...</label>

<input id="cb3" type="checkbox" class="input-l">
<label for="cb3">...</label>`, '#code-checkboxes');
    </script>


    <a name="color-selector"></a>
    <h3>Color Selectors</h3>
    <p>
        We created a special type of radio buttons and check boxes for you to easily implement a color selection.
        In this case you have to write a little custom scss to define the background color of the elements. You can also
        choose the color of the checkmark. Therefor you have to use the <code>color-selector-color</code> mixin which takes the background
        color as first argument and the checkmark color as a second one.
    </p>
    <div class="example example-color-picker">
        <div class="color-selector">
            <input id="as24-cb-cp-1" type="radio" name="xx" class="red">
            <label for="as24-cb-cp-1">red</label>

            <input id="as24-cb-cp-2" type="radio" name="xx" class="yellow">
            <label for="as24-cb-cp-2">yellow</label>

            <input id="as24-cb-cp-7" type="radio" name="xx" class="green">
            <label for="as24-cb-cp-7">green</label>

            <input id="as24-cb-cp-8" type="radio" name="xx" class="gold">
            <label for="as24-cb-cp-8">gold</label>
        </div>
        <div class="color-selector">
            <input id="as24-cb-cp-3" type="radio" name="xx" class="input-l blue">
            <label for="as24-cb-cp-3">radio</label>

            <input id="as24-cb-cp-4" type="radio" name="xx" class="input-l orange">
            <label for="as24-cb-cp-4">radio</label>
        </div>
        <div class="color-selector">
            <input id="as24-cb-cp-5" type="checkbox" name="xx" class="input-l blue">
            <label for="as24-cb-cp-5">radio</label>

            <input id="as24-cb-cp-6" type="checkbox" name="xx" class="input-l orange">
            <label for="as24-cb-cp-6">radio</label>
        </div>
    </div>
    <pre><code class="html" id="code-color-selector"></code></pre>
    <script>
        formatCode(`<div class="color-selector">
    <input id="cs1" type="radio" name="cs1" class="red">
    <label for="cs1">red</label>

    <input id="cs2" type="radio" name="cs1" class="yellow">
    <label for="cs2">yellow</label>

    <input id="cs3" type="radio" name="cs1" class="green">
    <label for="cs4">green</label>
</div>
-- additional scss --
@import "path/to/mixins/color-selector";
.color-selector {
    input {
        &.red {
            @include color-selector-color(#ff0000, fff);
        }
    -- gradient support --
        &.gold {
            @include color-selector-color(linear-gradient(brown, yellow, brown) gold);
        }
    }
}

-- radio buttons --
<div class="color-selector">
    <input id="..." type="radio" name="...">
    <label for="...">...</label>
</div>

-- checkboxes --
<div class="color-selector">
    <input id="..." type="checkbox" name="...">
    <label for="...">...</label>
</div>
`, '#code-color-selector');
    </script>

    <a name="input-groups"></a>
    <h3>Input Groups</h3>
    <div class="example example-groups">
        <div class="input-group">
            <input type="text" placeholder="Text input 1">
            <input type="text" placeholder="Text input 2">
            <button class="btn-bob-m">Submit</button>
        </div>

        <div class="input-group-radio">
            <input id="as24-radio-7" name="as24-radio" type="radio">
            <label for="as24-radio-7">Option 1</label>

            <input id="as24-radio-8" name="as24-radio" type="radio" checked>
            <label for="as24-radio-8">Option 2</label>

            <input id="as24-radio-9" name="as24-radio" type="radio">
            <label for="as24-radio-9">Option 3</label>
        </div>
    </div>
    <pre><code class="html" id="code-groups"></code></pre>
    <script>
        formatCode(`<div class="input-group">
    <input type="text">
    ...
</div>

<div class="input-group-radio">
    <input id="radio" type="radio">
    <label for="radio">...</label>
    ...
</div>`, '#code-groups');
    </script>
    <div>

        <p>To make the input groups work with <code>as24-icon</code> content, some additional css is needed:</p>
    </div>
    <div class="example example-groups">
        <div class="input-group-radio input-group-emission-badge">
            <input id="example-groups-3-1" name="example-groups-3" type="radio">
            <label for="example-groups-3-1">Alle</label>

            <input id="example-groups-3-2" name="example-groups-3" type="radio" checked>
            <label for="example-groups-3-2"><as24-icon type="emission-badge-2"></as24-icon></label>

            <input id="example-groups-3-3" name="example-groups-3" type="radio">
            <label for="example-groups-3-3"><as24-icon type="emission-badge-3"></as24-icon></label>

            <input id="example-groups-3-4" name="example-groups-3" type="radio">
            <label for="example-groups-3-4"><as24-icon type="emission-badge-4"></as24-icon></label>
        </div>
    </div>
    <pre><code class="html" id="code-groups-2-1"></code></pre>
    <script>
        formatCode(`<div class="input-group-radio" >
    ...
    <input id="radio" type="radio">
    <label for="radio"><as24-icon type="emission-badge-2"></as24-icon></label>
    ...
</div>
<!--
-- additional scss --
.your-selector {
    as24-icon {
        line-height: 0;
        display: block;

        svg {
            width: 24px;
            height: 24px;
        }
    }
}
-->`, '#code-groups-2-1');
    </script>
</div>
<div>
    <a name="helper"></a>
    <h2>Helper classes</h2>
    <a name="floats"></a>
    <h3>Floats</h3>
    <div class="example example-floats">
        <div class="clearfix">
            <div class="pull-left"></div>
            <div class="pull-left"></div>
            <div class="pull-left"></div>
        </div>
        <hr>
        <div class="clearfix">
            <div class="pull-right"></div>
            <div class="pull-right"></div>
            <div class="pull-right"></div>
        </div>
    </div>
    <pre><code class="html" id="code-floats"></code></pre>
    <script>
        formatCode(`<div class="clearfix">...</div>

<div class="pull-left">...</div>
<div class="pull-right">...</div>`, '#code-floats');
    </script>

    <a name="text-alignment"></a>
    <h3>Text alignment</h3>
    <div class="example example-text-alignment">
        <p class="text-left">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
        <hr>
        <p class="text-right">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
        <hr>
        <p class="text-center">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
        <hr>
        <p class="text-justify">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
        <hr>
        <p class="text-nowrap">Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
    </div>
    <pre><code class="html" id="code-text-alignment"></code></pre>
    <script>
        formatCode(`<p class="text-left">...</p>
<p class="text-right">...</p>
<p class="text-center">...</p>
<p class="text-justify">...</p>
<p class="text-nowrap">...</p>`, '#code-text-alignment');
    </script>

    <a name="center-blocks"></a>
    <h3>Center content blocks</h3>
    <div class="example example-block-center">
        <div class="block-center">.block-center</div>
    </div>
    <pre><code class="html" id="code-block-center"></code></pre>
    <script>
        formatCode(`<div class="block-center">...</div>`, '#code-block-center');
    </script>

    <a name="horizontal-line"></a>
    <h3>Horizontal line</h3>
    <p>To seperate some content you can use a horizontal line.</p>
    <div class="example example-horizontal-line">
        <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
        <hr>
        <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
    </div>
    <pre><code class="html" id="code-hr"></code></pre>
    <script>
        formatCode(`<hr>`, '#code-hr');
    </script>
</div>
<div>
    <a name="components"></a>
    <h2>Components</h2>

    <a name="collapse"></a>
    <h3>Collapse</h3>
    <div class="example example-collapse">
        <button class="btn-ross-m" data-toggle="collapse" data-target="#collapse-target-1">Collapse Toggle</button>
        <div id="collapse-target-1" class="collapse">
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
        </div>
        <hr>
        <button class="btn-ross-m collapse collapse-target in" data-toggle="collapse" data-target=".collapse-target">Collapse Show</button>
        <div class="collapse collapse-target">
            Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
        </div>
        <button data-toggle="collapse" data-target=".collapse-target" class="btn-ross-m collapse collapse-target">
            Collapse Hide
        </button>
    </div>

    <pre><code class="html" id="code-collapse"></code></pre>
    <script>
        formatCode(`<button data-toggle="collapse" data-target="#collapse">...</button>
<div id="collapse" class="collapse">...</div>

<button class="collapse collapse-target in" data-toggle="collapse" data-target=".collapse-target">Show</button>
<div class="collapse collapse-target">
    ...
</div>
<button data-toggle="collapse" data-target=".collapse-target" class="collapse collapse-target">Hide</button>`, '#code-collapse');
    </script>

    <a name="breadcrumbs"></a>
    <h3>Breadcrumbs</h3>
    <div class="example example-breadcrumbs">
        <div class="breadcrumbs">
            <ul>
                <li><a href="/url/to/home" data-breadcrumb="home">Home page</a></li>
                <li><a href="/url/to/list" data-breadcrumb="list">List results</a></li>
                <li><a href="/url/to/detail" data-breadcrumb="detail">Detail</a></li>
            </ul>
        </div>
    </div>
    <pre><code class="html" id="code-breadcrumbs"></code></pre>
    <script>
        formatCode(`<div class="breadcrumbs">
    <ul>
        <li><a href="/url/to/home" data-breadcrumb="home">Home page</a></li>
        <li><a href="/url/to/list" data-breadcrumb="list">List results</a></li>
        <li><a href="/url/to/detail" data-breadcrumb="detail">Detail</a></li>
    </ul>
</div>`, '#code-breadcrumbs');
    </script>

    <a name="custom-dropdown"></a>
    <h3>Custom Dropdown</h3>
    <div class="example example-custom-dropdown">
        <label>Custom Dropdown</label>
        <custom-dropdown checkboxgroup>
            <div>
                <p>All</p>
            </div>
            <div>
                <input type="checkbox" id="cd1"/>
                <label for="cd1">Value1</label>
                <input type="checkbox" id="cd2"/>
                <label for="cd2">Value2</label>
                <input type="checkbox" id="cd3"/>
                <label for="cd3">Value3</label>
            </div>
        </custom-dropdown>
    </div>
    <pre><code class="html" id="code-custom-dropdown"></code></pre>
    <script>
        formatCode(`<label>Custom Dropdown</label>
<custom-dropdown checkboxgroup>
    <div>
        <p>All</p>
    </div>
    <div>
        <input type="checkbox" id="myId"/>
        <label for="myId">My Label</label>
        ...
    </div>
</custom-dropdown>`, '#code-custom-dropdown');
    </script>
</div>

<script src="dist/showcar-ui.min.js"></script>

