# mgn-utility ( Don't Need jQuery )


Compiling function that can utilize descriptors similar to jQuery such as addClass, removeClass.

- Target browser : IE9+

___

# Install

```
npm i mgn-utility -S
```
## Or Download raw data
[↓ download "mgn-utility.js"](https://raw.githubusercontent.com/frontend-isobar-jp/mgn-utility/master/src/mgn-utility.js)

___

# Import

```
import { AddClass, RemoveClass, ... } from "mgn-utility"
```

___

# Property

|Property|If jQuer|
|:-------|:--------|
|AddClass( element, className ) *1|$(element).addClass(className)|
|RemoveClass( element, className )|$(element).removeClass(className)|
|HasClass( element, className )|$(element).hasClass(className)|
|SetCss( element, object ) *2|$(element).css(object)|
|GetParents( element, ".className or #id or tagName" )|$(element).parents(".className")|
|GetSiblings( element, ".className or #id or tagName" )|$(element).siblings(".className")|
|GetOffset( element ).top<br>GetOffset( element ).left|$(element).offset().top<br>$(element).offset().left|
|GetWidthData( element ).outerWidth|$(element).outerWidth()|
|GetHeightData( element ).outerHeight|$(element).outerHeight()|
|Not( element, ".className or #id" ) *3|$(element).not( “.className or #id” )|


___

# Demo

[https://frontend-isobar-jp.github.io/mgn-utility/](https://frontend-isobar-jp.github.io/mgn-utility/)

```
import { AddClass, SetCss, Not } from "mgn-utility"

/**
 * AddClass
 */
( () => {

    let element = document.getElementById('example'),
        element2 = document.getElementsByClassName('example');

    AddClass( element, "addClass");

    for (var i = 0; i < element2.length; i++) {
        AddClass( element2[i], "addClass");
    }

})();


/**
 * SetCss
 */
( () => {

    let element = document.getElementById('example2');

    SetCss( element, {
        "background": "#000",
        "color": "#FFF",
        "font-size": "20px"
    });

})();


/**
 * Not
 */
( () => {

    let element = document.getElementsByClassName('example3');

    for (var i = 0; i < element.length; i++) {
        element[i].onclick = (e) => {

            let not = Not( e.currentTarget, ".ignore" ); // true or false

            if( !not ) {
                alert("success !!")
            } else {
                alert("!! ignored element !!")
            }

        }
    }

})();
```
