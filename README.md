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
    <w-iframe w-onload="onload($handler)"></w-iframe>
</div>
```
**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onload = function (wiframeHandler) {
      scope.wiframeHandler = wiframeHandler;
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
    <w-iframe w-ondestroy="onDestroy($handler)"></w-iframe>
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
- [activate](#activate)

### activate
----
#### :page_with_curl: Description
this method is used to perform iframe component activation.

#### :bookmark_tabs: Parameters
**src:** _(String)_ Set the specific url.
**sandbox:** _(Enum)_ Set the sandbox type.
**Sandbox Types:** 
  DOWNLOADS: 'allow-downloads',
  ACTIVATION: 'allow-downloads-without-user-activation',
  FORMS: 'allow-forms',
  MODALS: 'allow-modals',
  ORIENTATION: 'allow-orientation-lock',
  POINTER: 'allow-pointer-lock',
  POPUPS: 'allow-popups',
  POPUPSCAPE: 'allow-popups-to-escape-sandbox',
  NAVIGATION: 'allow-top-navigation',
  STORAGE: 'allow-storage-access-by-user-activation',
  SCRIPTS: 'allow-scripts',
  ORIGIN: 'allow-same-origin',
  PRESENTATION: 'allow-presentation',
  PROTOCOLS: 'allow-top-navigation-to-custom-protocols',
  TOPNAVIGATION: 'allow-top-navigation-by-user-activation',

#### :leftwards_arrow_with_hook: Return
It return a object **Promise**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <w-iframe w-onblur="activate($handler)"></w-iframe>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.activate= function (handler) {
      handler.activate("https://test-teleconsultation-manager.sa1.hsdp.io/login", sandbox);
    }
  }
}
```
