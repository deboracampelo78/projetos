# Infoicon

This component is an icon that can be clicked to show additional information about fields on
dbpanel/cpanel.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)

#####

# HTML TAG:

```html
<w-infoicon></w-infoicon>
```

## Event Listeners

- [onLoad](#onLoad)
- [onClick](#onClick)

### onLoad

---

#### :clock230: When?

This event is fired before the component is loaded

#### :bookmark_tabs: Parameters

**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example
The event cannot be listened through Odin (Schematics).
It only can be listened by the HTML creator. Find the example on how to instance it through HTML below.

<b>HTML File</b>

```html
<w-infoicon></w-infoicon>
```

<b>Javascript File</b>

```javascript
//Call component handler
this.infoiconHandler = await getHandler(
  this.element.querySelector('w-infoicon')
);

//Listen to onLoad event from component
this.infoiconHandler.events.onLoad.addListener(() => this.doSomething());

doSomething(){
  //Do something here
}
```

### onClick

---

#### :clock230: When?

This event is fired when the Infoicon is clicked

#### :bookmark_tabs: Parameters

**handler:** _(Object)_ Component handler <br>

#### :pencil2: Example

The event cannot be listened through Odin (Schematics).
It only can be listened by the HTML creator. Find below the example on how to instantiate it through HTML.

<b>Parent HTML File</b>

```html
<w-infoicon></w-infoicon>
```

<b>Parent Javascript File</b>

```javascript
//Call component handler
this.infoiconHandler = await getHandler(
  this.element.querySelector('w-infoicon')
);

//Listen to onClick event from component
this.infoiconHandler.events.onClick.addListener(() => this.doSomething());

doSomething(){
  //Do something here
}
```

## Handler Methods

- [setInfoiconVisible](#setInfoiconVisible)
- [isInfoiconVisible](#isInfoiconVisible)

### setInfoiconVisible(true/false)

---

#### :page_with_curl: Description

Used to determine the component visibility

#### :bookmark_tabs: Parameters

**visible:** _(Object)_ True/False for component visibility <br>

#### :leftwards_arrow_with_hook: Return

Not available

#### :pencil2: Example

```javascript
infoiconHandler.setInfoiconVisible(true); //show the component
infoiconHandler.setInfoiconVisible(false); //hide the component
```

### isInfoiconVisible

---

#### :page_with_curl: Description

Gets infoicon visibility (true/false)
(Returns true when the infoicon is visible)

#### :bookmark_tabs: Parameters

Not available

#### :leftwards_arrow_with_hook: Return

Boolean

#### :pencil2: Example

```javascript
if (infoiconHandler.isInfoiconVisible()) {
  // Do something
}
```

## Component Diagram
----
![Component Diagram](./../../../../assets/framework/w-infoicon/docs/wInfoiconDiagram.png)

### Component Diagram XML
- <a href="https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/assets/framework/w-infoicon/docs/wInfoiconDiagram.xml" target="_blank">Component Diagram XML</a>

