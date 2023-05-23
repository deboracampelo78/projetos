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
      scope.wiframeHandler.setButtonVisible(false);
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
        delete scope.iframeSource;
        delete scope.wiframeHandler;
    };

  }
}
```
## Handler Methods
- [onActivate](#onActivate)

### onActivate
----
#### :page_with_curl: Description
This method is used to add the url and the sandbox inside the iframe.

#### :bookmark_tabs: Parameters
**iframe:** _(File)_  Set the specific url and sandbox.

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

## Component Diagram
![Component Diagram](./../../../../assets/framework/w-image/docs/wImageDiagram.png)

### Component Diagram XML
To create the diagram was used the online plataform https://www.draw.io/. <br>

- <a href="https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/assets/framework/w-image/docs/wImageDiagram.xml" target="_blank">Component Diagram XML</a>
