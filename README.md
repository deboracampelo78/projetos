# Iframe
This component creates an Iframe, to be rendered inside the system screen.

- [Event Listeners](#Event-Listeners)
- [Handler Methods](#Handler-Methods)
- [Component Diagram](#component-diagram)

## Event Listeners
- [onLoad](#onLoad)
- [onDestroy](#onDestroy)

### onLoad
----
#### :clock230: When?
This event is fired after the component is loaded.<br>
The event cannot be listen through Odin (Schematics).<br>
It only can be listen by the HTML creator, see on exemple section.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic. <br>
**handler:** _(Object)_ Component handler. <br>
**event:** Not available

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wiframe w-onload="onload($handler)"></tasy-wiframe>
</div>
```
**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onload = function (wiframeHandler) {
      scope.wiframeHandler = wiframeHandler;
      scope.wiframeHandler.attributeInfo.setReadOnly(true);
    }

  }
}
```

### onDestroy
----
#### :clock230: When?
This event is fired after the component is finalized.<br>
The event cannot be listen through Odin (Schematics).<br>
It only can be listen by the HTML creator, see on exemple section.

#### :bookmark_tabs: Parameters
**schematic:** _(Object)_  Function schematic. <br>
**handler:** _(Object)_ Component handler. <br>
**event:** Not available

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wiframe w-ondestroy="onDestroy($handler)"></tasy-wiframe>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onDestroy = () => {
        // call data to be destroyed
    };
  }
}
```
## Handler Methods
- [onActivate](#onActivate)

### onActivate
----
#### :page_with_curl: Description
this method is used to activate the iframe component.

#### :bookmark_tabs: Parameters
**iframe:**
_(String)_ src -  Set the specific url.
_(Enum)_ sandbox -  Set the specific sandbox type.

#### :leftwards_arrow_with_hook: Return
It return a object **Promise**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wiframe w-onblur="onActivate($handler)"></tasy-wiframe>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onActivate= function (handler) {
      handler.onActivate("https://test-teleconsultation-manager.sa1.hsdp.io/login", sandbox);
    }
  }
}
```
