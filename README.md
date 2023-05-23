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
    <tasy-wimage w-ondestroy="onDestroy($handler)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onDestroy = () => {
        delete scope.imageSource;
        delete scope.wimageHandler;
    };

  }
}
```

### onSubmit
----
#### :clock230: When?
This event is fired when an image is uploaded to the server.<br>
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
    <tasy-wimage w-onsubmit="onSubmit($handler, $event)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wCarga(textresources) {

  function linkFunc(scope) {

    function onSubmit(handler, event) {
      if (event.status === 'OK') {
        viewMessage(390055);
      } else {
        viewMessage(390054);
      }
    }

    function viewMessage(code) {
      textresources.get(code).then((response) => {
          scope.msgsucesso = response;
        }
      );
    }

  }
}

```

### onRightClick
----
#### :clock230: When?
This event is fired when the user clicks the right mouse button.<br>
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
    <tasy-wimage w-onrightclick="onRightClick($handler)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.onRightClick = function () {
      scope.wimageHandler.attributeInfo.setReadOnly(false);
    }

  }
}
```

### onBlur
----
#### :clock230: When?
This event is fired when the upload image element loses focus.<br>
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
    <tasy-wimage w-onblur="onBlur($handler)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.onBlur = function (handler) {
      handler.resetZoom();
      handler.rotateCW();
    }

  }
}
```

### onChange
----
#### :clock230: When?
This event is fired when the image is changed.<br>
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
    <tasy-wimage w-ready="onChange($handler)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.onChange = function (handler) {
      handler.setTitle('Image changed');
      handler.resetZoom();
    }

  }
}
```

### onReady
----
#### :clock230: When?
This event is fired when the wConfigPreview is altered and model have base64 image or path image.<br>
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
    <tasy-wimage w-ready="onReady($handler)"></tasy-wimage>
</div>
```
**Javascript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onReady = function (wimageHandler) {
      scope.wimageHandler = wimageHandler;
      scope.wimageHandler.attributeInfo.setReadOnly(false);
      scope.wimageHandler.useCustomSize(true);
    }

  }
}
```

## Handler Methods
- [addImage](#addImage)
- [getValue](#getValue)
- [setValue](#setValue)
- [getPrettyValue](#getPrettyValue)
- [useCustomSize](#useCustomSize)
- [send](#send)
- [getBase64Image](#getBase64Image)
- [setBase64Image](#setBase64Image)
- [isBase64Attribute](#isBase64Attribute)
- [setFormName](#setFormName)
- [activateByPath](#activateByPath)
- [canSelect](#canSelect)
- [setFocus](#setFocus)
- [setTitle](#setTitle)
- [getTitle](#getTitle)
- [getDimensions](#getDimensions)
- [getImageDepth](#getImageDepth)
- [isSensitive](#isSensitive)
- [setButtonVisible](#setButtonVisible)
- [setAcceptedFiles](#setAcceptedFiles)
- [zoomOut](#zoomOut)
- [zoomIn](#zoomIn)
- [resetZoom](#resetZoom)
- [rotateCW](#rotateCW)
- [captureImage](#captureImage)

### addImage
----
#### :page_with_curl: Description
This method is used to add a image file in the server.

#### :bookmark_tabs: Parameters
**image:** _(File)_  Set the specific image.

#### :leftwards_arrow_with_hook: Return
It return a object **Promise**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onblur="addImage($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.addImage = function (handler) {
      return scope.addImage(scope.selectedImage).then(event => event);
    }

  }
}
```

### getValue
----
#### :page_with_curl: Description
This method is used to get the image file.

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
It return a object **File**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="getValue($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope, WStore) {

    const store = new WStore().unsubscribable();
    
    $scope.getValue = function (handler) {
      store.notify('image', handler.getValue());
    };
}
```

### setValue
----
#### :page_with_curl: Description
In this method you can set specific image file.

#### :bookmark_tabs: Parameters
**image:** _(File)_  Set the specific image.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="changeImage($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.changeImage = function (handler) {
      handler.setValue($scope.selectedImage);
      store.notify('selectedImage');
    };
}
```

### getPrettyValue
----
#### :page_with_curl: Description
In this method you can get the title with a promise

#### :bookmark_tabs: Parameters
Not available

#### :leftwards_arrow_with_hook: Return
It return a object **Promise**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="getPrettyValue($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.getPrettyValue = function (handler) {
      $scope.handler.getPrettyValue().then(value => store.set('title', value));
    };
}
```

### useCustomSize
----
#### :page_with_curl: Description
In this method you can use a custom size at image preview.<br>
The default value is false.

#### :bookmark_tabs: Parameters
**val:** _(boolean)_  Set true or false.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="useCustomSize($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.onload = function (wimageHandler) {
      scope.wimageHandler = wimageHandler;
      scope.wimageHandler.useCustomSize(true);
      scope.wimageHandler.setButtonVisible(false);
    }

  }
}
```

### send
----
#### :page_with_curl: Description
This method is used to send the selected image file to the server.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a object **Promise**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onchange="sendImage($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.sendImage = function (handler) {
      handler.send().then(() => handler.setButtonVisible(true));
    }

  }
}
```

### getBase64Image
----
#### :page_with_curl: Description
This method is used to get the selected image file as base64.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return the encoded string in base64 **string**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onchange="getImage($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.getImage = function (handler) {
      scope.selectedImage = handler.getImage();
      store.set('imageBase64', scope.selectedImage);
    };
}
```

### setBase64Image
----
#### :page_with_curl: Description
This method is used to set the selected image file as base64.

#### :bookmark_tabs: Parameters
**value:** _(Object)_ Set base64 image.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onchange="changeBase64Image($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.changeBase64Image = function (handler) {
      const img = store.get('imageBase64');
      handler.setBase64Image(img);
      scope.selectedImage = img;
    };
}
```

### isBase64Attribute
----
#### :page_with_curl: Description
This method returns true if the file is saved as Base64.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a boolean **Boolean**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="isBaseSave($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.isBaseSave = function (handler) {

      if(handler.isBase64Attribute()){
        store.notify('saveInBase64');
      } else {
        store.notify('notSaveInBase64');
      }

    };
}
```

### setFormName
----
#### :page_with_curl: Description
This method is used to add a field form in the component.

#### :bookmark_tabs: Parameters
**value:** _(element)_ Set a field form.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="setFormName($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope, element) {

    scope.setFormName = function (handler) {
      const fieldForm = element.find('input').controller('ngModel');
      handler.setFormName(fieldForm);
      handler.activateByPath(scope.pathImage);
      
    }

  }
}
```

### activateByPath
----
#### :page_with_curl: Description
This method is used to activate the component by the path of a image.

#### :bookmark_tabs: Parameters
**value:** _(String)_ Set path the image.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="activate($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.activate = function (handler) {
      handler.activateByPath(scope.pathImage);
    }

  }
}
```

### canSelect
----
#### :page_with_curl: Description
This method is used to enable/disable the selection of a new image.<br>
The default value is true.

#### :bookmark_tabs: Parameters
**value:** _(Boolean)_ Set true or false.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="canSelect($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.canSelect = function (handler) {
      handler.canSelect(false);
      handler.setButtonVisible(false);
    }

  }
}
```

### setFocus
----
#### :page_with_curl: Description
This method is used to set focus at input element

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="inputFocus($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.inputFocus = function (handler) {
      handler.setFocus();
      handler.setButtonVisible(true);
    }

  }
}
```

### setTitle
----
#### :page_with_curl: Description
This method is used to set a title to the component.

#### :bookmark_tabs: Parameters
**value:** _(String)_ Set a title.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="setTitle($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.setTitle = function (handler) {
      handler.activateByPath(scope.pathImage);
      handler.setTitle('My title of the component');
      handler.setButtonVisible(false);
    }

  }
}
```

### getTitle
----
#### :page_with_curl: Description
This method is used to get the title applied to the component.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a string **String**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="getTitle($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.getTitle = function (handler) {
      handler.setFocus();
      store.set('title', handler.getTitle());

    };
}
```

### getDimensions
----
#### :page_with_curl: Description
This method is used to get a dimensions of the image selected.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a object **Object**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="saveDimensions($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope, $element) {

    const store = new WStore().unsubscribable();
    
    $scope.saveDimensions = function (handler) {

      const image = $element[0].querySelector('.image');
      image.width = handler.getDimensions().width;
      image.height = handler.getDimensions().height;
      store.notify('changedDimensions');

    };
}
```

### getImageDepth
----
#### :page_with_curl: Description
This method is used to get a color depth of the image.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a number **number**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="getImageDepth($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export default function wNotificationController($scope) {

    const store = new WStore().unsubscribable();
    
    $scope.getImageDepth = function (handler) {
      const imgDepth = handler.getImageDepth();
      store.set('imgDepth', imgDepth);
    };
}
```

### isSensitive
----
#### :page_with_curl: Description
This method is used to identify if the button is readonly.
The default value is undefined.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
It return a boolean or undefined **boolean/undefined**<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="isSensitive($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.isSensitive = function (handler) {
      const isSensitive = handler.isSensitive();
      handler.setButtonVisible(isSensitive);
      handler.setTitle('Is not sensitive');
      if (isSensitive) {
        handler.setTitle('Is sensitive');
      }
      
    }

  }
}
```

### setButtonVisible
----
#### :page_with_curl: Description
This method is used to show or hide the button on choose image.<br>
The default value is true.

#### :bookmark_tabs: Parameters
**value:** _(Boolean)_ Set false for hidden ou true for visible.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="setButtonVisible($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.setButtonVisible = function (handler) {
      handler.setFocus();
      handler.setButtonVisible(true);
    }

  }
}
```

### setAcceptedFiles
----
#### :page_with_curl: Description
This method is used to set accepted files in the component.
The default value is `image/*`.

#### :bookmark_tabs: Parameters
**acceptedFiles:** _(String)_ Set the string value.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="setAcceptedFiles($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg(wTwainService, WEvent) {
  'ngInject';

  function linkFunc(scope) {

    scope.setAcceptedFiles = function (handler) {
      handler.setAcceptedFiles(".png");
    }

  }
}
```

### zoomOut
----
#### :page_with_curl: Description
This method is used to decrease zoom in the selected image.

#### :bookmark_tabs: Parameters
**value:** _(int)_ Set the number value.<br>
**ignoreLimit:** _(boolean)_ Set the boolean true or false.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="zoomOut($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.zoomOut = function (handler) {
      handler.setFocus();
      handler.zoomOut(5, true);
    }

  }
}
```

### zoomIn
----
#### :page_with_curl: Description
This method is used to increase zoom in the selected image.

#### :bookmark_tabs: Parameters
**value:** _(int)_ Set the number value.<br>
**ignoreLimit:** _(boolean)_ Set the boolean true or false.

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="zoomIn($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.zoomIn = function (handler) {
      handler.setFocus();
      handler.zoomIn(5, true);
    }

  }
}
```

### resetZoom
----
#### :page_with_curl: Description
This method is used to reset the zoom on the selected image to the default.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-ready="resetZoom($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.zoomIn = function (handler) {
      handler.setFocus();
      handler.resetZoom();
    }

  }
}
```

### rotateCW
----
#### :page_with_curl: Description
This method is used to rotate the selected image in 90 deegrees.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="rotateCW($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.rotateCW = function (handler) {
      handler.setFocus();
      handler.rotateCW();
    }

  }
}
```

### captureImage
----
#### :page_with_curl: Description
This method is used for capture the image with tasy-wcapture component.

#### :bookmark_tabs: Parameters
Not available<br>

#### :leftwards_arrow_with_hook: Return
Not available<br>

#### :pencil2: Example
**HTML File:**
```html
<div>
    <tasy-wimage w-onload="captureImage($handler)"></tasy-wimage>
</div>
```

**JavaScript File:**
```javascript
export function wTwainDlg() {
  'ngInject';

  function linkFunc(scope) {

    scope.captureImage = function (handler) {
      handler.resetZoom();
      handler.captureImage();
      
    }

  }
}
```

## Component Diagram
![Component Diagram](./../../../../assets/framework/w-image/docs/wImageDiagram.png)

### Component Diagram XML
To create the diagram was used the online plataform https://www.draw.io/. <br>

- <a href="https://github.com/philips-emr/tasy-framework/blob/dev/packages/framework/src/assets/framework/w-image/docs/wImageDiagram.xml" target="_blank">Component Diagram XML</a>
