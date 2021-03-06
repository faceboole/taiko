<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [openBrowser](#openbrowser)
-   [closeBrowser](#closebrowser)
-   [goto](#goto)
-   [reload](#reload)
-   [click](#click)
-   [doubleClick](#doubleclick)
-   [rightClick](#rightclick)
-   [hover](#hover)
-   [focus](#focus)
-   [write](#write)
-   [upload](#upload)
-   [press](#press)
-   [highlight](#highlight)
-   [scrollTo](#scrollto)
-   [scrollRight](#scrollright)
-   [scrollLeft](#scrollleft)
-   [scrollUp](#scrollup)
-   [scrollDown](#scrolldown)
-   [screenshot](#screenshot)
-   [$](#)
-   [$$](#-1)
-   [image](#image)
-   [link](#link)
-   [listItem](#listitem)
-   [button](#button)
-   [inputField](#inputfield)
-   [textField](#textfield)
-   [comboBox](#combobox)
-   [checkBox](#checkbox)
-   [radioButton](#radiobutton)
-   [text](#text)
-   [contains](#contains)
-   [alert](#alert)
-   [prompt](#prompt)
-   [confirm](#confirm)
-   [beforeunload](#beforeunload)
-   [intervalSecs](#intervalsecs)
-   [timeoutSecs](#timeoutsecs)
-   [waitForNavigation](#waitfornavigation)
-   [to](#to)
-   [into](#into)
-   [browser](#browser)
-   [page](#page)
-   [selector](#selector)
-   [ElementWrapper](#elementwrapper)

## openBrowser

Launches a browser with a tab. The browser will be closed when the parent node.js process is closed.

**Parameters**

-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Set of configurable [options](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#puppeteerlaunchoptions) to set on the browser.

**Examples**

```javascript
openBrowser()
openBrowser({ headless: false })
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## closeBrowser

Closes the browser and all of its tabs (if any were opened).

**Examples**

```javascript
closeBrowser()
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## goto

Opens the specified URL in the browser's tab. Adds `http` protocol to the URL if not present.

**Parameters**

-   `url` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** URL to navigate page to.
-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** [Navigation parameters](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#pagegotourl-options)

**Examples**

```javascript
goto('https://google.com')
goto('google.com')
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed and the final URL.

## reload

Reloads the page.

**Parameters**

-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** [Navigation parameters](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#pagereloadoptions)

**Examples**

```javascript
reload('https://google.com')
reload('https://google.com', { timeout: 10000 })
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed and the final URL.

## click

Fetches an element with the given selector, scrolls it into view if needed, and then clicks in the center of the element. If there's no element matching selector, the method throws an error.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector to search for element to click. If there are multiple elements satisfying the selector, the first will be clicked.
-   `waitForNavigation` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** Wait for navigation after the click. Default navigation timout is 5 seconds, to override pass `{ timeout: 10000 }` in `options` parameter. (optional, default `true`)
-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Click options.
    -   `options.button` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** `left`, `right`, or `middle`. (optional, default `'left'`)
    -   `options.number` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Number of times to click on the element. (optional, default `1`)
    -   `options.delay` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Time to wait between mousedown and mouseup in milliseconds. (optional, default `0`)
    -   `options.timeout` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Timeout value in milliseconds for navigation after click. (optional, default `5000`)

**Examples**

```javascript
click('Get Started')
click(link('Get Started'))
click('Get Started', waitForNavigation(false))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## doubleClick

Fetches an element with the given selector, scrolls it into view if needed, and then double clicks the element. If there's no element matching selector, the method throws an error.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector to search for element to click. If there are multiple elements satisfying the selector, the first will be double clicked.
-   `waitForNavigation` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** wait for navigation after the click. (optional, default `true`)

**Examples**

```javascript
doubleClick('Get Started')
doubleClick(button('Get Started'))
doubleClick('Get Started', waitForNavigation(false))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## rightClick

Fetches an element with the given selector, scrolls it into view if needed, and then right clicks the element. If there's no element matching selector, the method throws an error.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector to search for element to right click. If there are multiple elements satisfying the selector, the first will be double clicked.

**Examples**

```javascript
rightClick('Get Started')
rightClick(text('Get Started'))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## hover

Fetches an element with the given selector, scrolls it into view if needed, and then hovers over the center of the element. If there's no element matching selector, the method throws an error.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector to search for element to right click. If there are multiple elements satisfying the selector, the first will be hovered.

**Examples**

```javascript
hover('Get Started')
hover(link('Get Started'))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## focus

Fetches an element with the given selector and focuses it. If there's no element matching selector, the method throws an error.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector of an element to focus. If there are multiple elements satisfying the selector, the first will be focused.

**Examples**

```javascript
focus(textField('Username:'))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## write

Types the given text into the focused or given element.

**Parameters**

-   `text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Text to type into the element.
-   `into` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))?** A selector of an element to write into.

**Examples**

```javascript
write('admin', into('Username:'))
write('admin', 'Username:')
write('admin')
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## upload

Uploads a file to a file input element.

**Parameters**

-   `filepath` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The path of the file to be attached.
-   `to` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** The file input element to which to upload the file.

**Examples**

```javascript
upload('c:/abc.txt', to('Please select a file:'))
upload('c:/abc.txt', 'Please select a file:')
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## press

Presses the given key.

**Parameters**

-   `key` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Name of key to press, such as ArrowLeft. See [USKeyboardLayout](https://github.com/GoogleChrome/puppeteer/blob/master/lib/USKeyboardLayout.js) for a list of all key names.
-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `options.text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** If specified, generates an input event with this text.
    -   `options.delay` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Time to wait between keydown and keyup in milliseconds. (optional, default `0`)

**Examples**

```javascript
press('Enter')
press('a')
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## highlight

Highlights the given element on the page by drawing a red rectangle around it. This is useful for debugging purposes.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector of an element to highlight. If there are multiple elements satisfying the selector, the first will be highlighted.

**Examples**

```javascript
highlight('Get Started')
highlight(link('Get Started'))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## scrollTo

Scrolls the page to the given element.

**Parameters**

-   `selector` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String))** A selector of an element to scroll to.

**Examples**

```javascript
scrollTo('Get Started')
scrollTo(link('Get Started'))
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## scrollRight

Scrolls the page/element to the right.

**Parameters**

-   `e` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number))**  (optional, default `'Window'`)
-   `px` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)**  (optional, default `100`)

**Examples**

```javascript
scrollRight()
scrollRight(1000)
scrollRight('Element containing text')
scrollRight('Element containing text', 1000)
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## scrollLeft

Scrolls the page/element to the left.

**Parameters**

-   `e` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number))**  (optional, default `'Window'`)
-   `px` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)**  (optional, default `100`)

**Examples**

```javascript
scrollLeft()
scrollLeft(1000)
scrollLeft('Element containing text')
scrollLeft('Element containing text', 1000)
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## scrollUp

Scrolls up the page/element.

**Parameters**

-   `e` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number))**  (optional, default `'Window'`)
-   `px` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)**  (optional, default `100`)

**Examples**

```javascript
scrollUp()
scrollUp(1000)
scrollUp('Element containing text')
scrollUp('Element containing text', 1000)
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## scrollDown

Scrolls down the page/element.

**Parameters**

-   `e` **([selector](#selector) \| [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number))**  (optional, default `'Window'`)
-   `px` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)**  (optional, default `100`)

**Examples**

```javascript
scrollDown()
scrollDown(1000)
scrollDown('Element containing text')
scrollDown('Element containing text', 1000)
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)>** Object with the description of the action performed.

## screenshot

Captures a screenshot of the page.

**Parameters**

-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options object with properties mentioned [here](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#pagescreenshotoptions).

**Examples**

```javascript
screenshot({path: 'screenshot.png'});
```

Returns **[Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Buffer](https://nodejs.org/api/buffer.html)>** Promise which resolves to buffer with captured screenshot.

## $

This [selector](#selector) lets you identify an element on the web page via XPath or CSS selector.

**Parameters**

-   `selector` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** XPath or CSS selector.

**Examples**

```javascript
click($('.class'))
$('.class').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## $$

This [selector](#selector) lets you identify elements on the web page via XPath or CSS selector.

**Parameters**

-   `selector` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** XPath or CSS selector.

**Examples**

```javascript
highlight($$(`//*[text()='text']`)[1])
$$(`//*[text()='text']`).exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## image

This [selector](#selector) lets you identify an image (HTML <img> element) on a web page. Typically, this is done via the image's alt text.

**Parameters**

-   `alt` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The image's alt text.

**Examples**

```javascript
click(image('alt'))
image('alt').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## link

This [selector](#selector) lets you identify a link on a web page.

**Parameters**

-   `text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The link text.

**Examples**

```javascript
click(link('Get Started'))
link('Get Started').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## listItem

This [selector](#selector) lets you identify a list item (HTML <li> element) on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The label of the list item.

**Examples**

```javascript
highlight(listItem('Get Started'))
listItem('Get Started').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## button

This [selector](#selector) lets you identify a button on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The button label.

**Examples**

```javascript
highlight(button('Get Started'))
button('Get Started').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## inputField

This [selector](#selector) lets you identify an input field on a web page.

**Parameters**

-   `attribute` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The input field's attribute. (optional, default `'value'`)
-   `value` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Value of the attribute specified in the first parameter.

**Examples**

```javascript
focus(inputField('id', 'name'))
inputField('id', 'name').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## textField

This [selector](#selector) lets you identify a text field on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The label (human-visible name) of the text field.

**Examples**

```javascript
focus(textField('Username:'))
textField('Username:').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## comboBox

This [selector](#selector) lets you identify a combo box on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The label (human-visible name) of the combo box.

**Examples**

```javascript
comboBox('Vehicle:').select('Car')
comboBox('Vehicle:').value()
comboBox('Vehicle:').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## checkBox

This [selector](#selector) lets you identify a checkbox on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The label (human-visible name) of the check box.

**Examples**

```javascript
checkBox('Vehicle').check()
checkBox('Vehicle').uncheck()
checkBox('Vehicle').isChecked()
checkBox('Vehicle').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## radioButton

This [selector](#selector) lets you identify a radio button on a web page.

**Parameters**

-   `label` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** The label (human-visible name) of the radio button.

**Examples**

```javascript
radioButton('Vehicle').select()
radioButton('Vehicle').deselect()
radioButton('Vehicle').isSelected()
radioButton('Vehicle').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## text

This [selector](#selector) lets you identify an element with text.

**Parameters**

-   `text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Text to match.

**Examples**

```javascript
highlight(text('Vehicle'))
text('Vehicle').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## contains

This [selector](#selector) lets you identify an element containing the text.

**Parameters**

-   `text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Text to match.

**Examples**

```javascript
contains('Vehicle').exists()
```

Returns **[ElementWrapper](#elementwrapper)** 

## alert

Lets you perform an operation when an `alert` with given text is shown.

**Parameters**

-   `message` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Identify alert based on this message.
-   `callback` **function ([alert](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert))** Operation to perform.

**Examples**

```javascript
alert('Message', async alert => await alert.dismiss());
```

## prompt

Lets you perform an operation when a `prompt` with given text is shown.

**Parameters**

-   `message` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Identify prompt based on this message.
-   `callback` **function ([prompt](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt))** Operation to perform.

**Examples**

```javascript
prompt('Message', async prompt => await prompt.dismiss());
```

## confirm

Lets you perform an operation when a `confirm` with given text is shown.

**Parameters**

-   `message` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Identify confirm based on this message.
-   `callback` **function ([confirm](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm))** Operation to perform.

**Examples**

```javascript
confirm('Message', async confirm => await confirm.dismiss());
```

## beforeunload

Lets you perform an operation when a `beforeunload` with given text is shown.

**Parameters**

-   `message` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Identify beforeunload based on this message.
-   `callback` **function (beforeunload)** Operation to perform.

**Examples**

```javascript
beforeunload('Message', async beforeunload => await beforeunload.dismiss());
```

## intervalSecs

Converts seconds to milliseconds.

**Parameters**

-   `secs` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Seconds to convert.

**Examples**

```javascript
link('Plugins').exists(intervalSecs(1))
```

Returns **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Milliseconds.

## timeoutSecs

Converts seconds to milliseconds.

**Parameters**

-   `secs` **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Seconds to convert.

**Examples**

```javascript
link('Plugins').exists(intervalSecs(1), timeoutSecs(10))
```

Returns **[number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Milliseconds.

## waitForNavigation

This function is used to improve the readability. It simply returns the parameter passed into it.

**Parameters**

-   `e` **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 

**Examples**

```javascript
click('Get Started', waitForNavigation(false))
```

Returns **[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** 

## to

This function is used to improve the readability. It simply returns the parameter passed into it.

**Parameters**

-   `e`  

**Examples**

```javascript
upload('c:/abc.txt', to('Please select a file:'))
```

Returns **([string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [selector](#selector))** 

## into

This function is used to improve the readability. It simply returns the parameter passed into it.

**Parameters**

-   `e`  

**Examples**

```javascript
write("user", into('Username:'))
```

Returns **([string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) \| [selector](#selector))** 

## browser

Returns the browser insance created using openBrowser.

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Puppeteer's [Browser](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#class-browser) instance.

## page

Returns the page instance.

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** Puppeteer's [Page](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md#class-page) instance.

## selector

Identifies an element on the page.

Type: [Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)

**Parameters**

-   `text` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Text to identify the element.
-   `args` **...[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** 

**Examples**

```javascript
link('Sign in')
button('Get Started')
$('#id')
text('Home')
```

## ElementWrapper

Wrapper object for the element present on the web page. Extra methods are avaliable based on the element type.

-   `get()`, `exists()`, `description` for all the elements.
-   `value()` for input field and text field.
-   `value()`, `select()` for combo box.
-   `check()`, `uncheck()`, `isChecked()` for checkbox.
-   `select()`, `deselect()`, `isSelected()` for radio button.

Type: [Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

**Properties**

-   `exists` **function ([number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number), [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number))** Checks existence for element.
-   `description` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Describing the operation performed.

**Examples**

```javascript
link('google').exists()
link('google').exists(intervalSecs(1), timeoutSecs(10))
link('google').description
textField('username').value()
```
