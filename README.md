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
**src:** _(String)_ Set the specific url.<br>
**sandbox:** _(Enum)_ Set the sandbox type.<br>
**Sandbox Types:** 
  DOWNLOADS: 'allow-downloads',<br>
  ACTIVATION: 'allow-downloads-without-user-activation',<br>
  FORMS: 'allow-forms',<br>
  MODALS: 'allow-modals',
  ORIENTATION: 'allow-orientation-lock',<br>
  POINTER: 'allow-pointer-lock',<br>
  POPUPS: 'allow-popups',<br>
  POPUPSCAPE: 'allow-popups-to-escape-sandbox',<br>
  NAVIGATION: 'allow-top-navigation',<br>
  STORAGE: 'allow-storage-access-by-user-activation',<br>
  SCRIPTS: 'allow-scripts',<br>
  ORIGIN: 'allow-same-origin',<br>
  PRESENTATION: 'allow-presentation',<br>
  PROTOCOLS: 'allow-top-navigation-to-custom-protocols',<br>
  TOPNAVIGATION: 'allow-top-navigation-by-user-activation',<br><br>
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
