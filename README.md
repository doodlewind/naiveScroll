# naiveScroll
Tiny jQuery full page scroll effect plugin.

## Features
* Override mouse whell event to scroll full page.
* Minimum extra HTML elements required.
* Prevents redundant events from being triggered.
* Provide API to manually scroll up or down.
* Tiny size, 1KB zipped.

## Usage

### HTML
Simply use basic `<section>` element to contain the pages you need to scroll. No other class or properties is required. You can also modify JS code to use other DOM element as container.

``` html
<body>
    <section></section>
    <section></section>
    <section></section>
</body>
```

### CSS
You can custom the HTML `<section>` created above as you like. For example, you can use diffferent background images for each `<section>` as below.

Firstly add some classes to distinguish each class.

``` html
<body>
    <section class="page1"></section>
    <section class="page2"></section>
    <section class="page3"></section>
</body>
```

Then custom each sections with your styles.

``` css
/* use background color */
.page1 {
    top: 0;
    background-color: lightcoral;
}

/* or use background image */
.page2 {
    top: 100%;
    background: url("foo.jpg") no-repeat center center;
    background-size: cover;
}

/* notice the top property */
.page3 {
    top: 200%;
    background-color: lightblue;
}
```

### JS
Once you finish the static content, you can easily enable naiveScroll with jQuery.

#### Enable mouse wheel scroll effect
Just call `init` method and test it out.

``` js
$(this)._naiveScroll.init();
```

#### Bind scroll effect to other events
Now naiveScroll only supports scroll up or down one page per time. You can modify its source code to support your compenents.

``` js
$('#upBtn').click(function () {
    $(this)._naiveScroll.triggerScroll(100);
});
    
$('#downBtn').click(function () {
    $(this)._naiveScroll.triggerScroll(-100);
});
```

Have fun!
