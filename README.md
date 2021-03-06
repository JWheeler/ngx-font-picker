# Angular Font Picker

<a href="https://badge.fury.io/js/ngx-font-picker"><img src="https://badge.fury.io/js/ngx-font-picker.svg" align="right" alt="npm version" height="18"></a>

This is a simple font picker loosely based on the cool angular2-color-picker by Alberplz.

This documentation is for the latest 5.x.x version which requires Angular 5. For Angular 4 you need to use the latest 4.x.x version. Documentation for the 4.x.x can be found from <a href="https://github.com/zefoy/ngx-font-picker/tree/4.x.x/">here</a>.

### Quick links

[Example application](https://zefoy.github.io/ngx-font-picker/)
 | 
[Plunker template](http://plnkr.co/edit/UpJA4eUZD76YK2Eh95B8?p=preview)

### Building the library

```bash
npm install
npm start
```

### Running the example

```bash
cd example
npm install
npm start
```

### Library development


```bash
npm link
cd example
npm link ngx-font-picker
```

### Installing and usage

```bash
npm install ngx-font-picker --save
```

##### Load the module for your app (with global configuration):

```javascript
import { FontPickerModule } from 'ngx-font-picker';
import { FONT_PICKER_CONFIG } from 'ngx-font-picker';
import { FontPickerConfigInterface } from 'ngx-font-picker';

const DEFAULT_FONT_PICKER_CONFIG: FontPickerConfigInterface = {
  // Change this to your Google API key
  apiKey: 'AIzaSyA9S7DY0khhn9JYcfyRWb1F6Rd2rwtF_mA'
};

@NgModule({
  ...
  imports: [
    ...
    FontPickerModule
  ],
  providers: [
    {
      provide: FONT_PICKER_CONFIG,
      useValue: DEFAULT_FONT_PICKER_CONFIG
    }
  ]
})
```

##### Use it in your HTML template (for example in div element):

```html
<div [(fontPicker)]="font" [fpWidth]="'320px'" [fpPosition]="'bottom'">
  Click to open the font picker
</div>
```

```javascript
[(fontPicker)]          // Selected font ({family, size, style, styles, files}).

[fpWidth]               // Width of the font picker (Default: '280px').
[fpHeight]              // Height of the font picker (Default: '320px').

[fpPosition]            // Position of the font picker (Default: 'bottom').

[fpAutoLoad]            // Auto loads font on change (fontPicker input change).

[fpSizeSelect]          // Show size selector in the font picker (Default: false).

[fpStyleSelect]         // Show style selector in the font picker (Default: false).

[fpPresetLabel]         // Label for the preset fonts list (Default: undefined).
[fpPresetFonts]         // Listing of preset fonts to show (Default: undefined).

[fpFallbackFont]        // Fallback font (Default: {family: 'Roboto', size: 14}).

[fpCancelButton]        // Show cancel button in the font picker (Default: false).

[fpUploadButton]        // Show upload button in the font picker (Default: false).

(fontPickerChange)      // Event handler for the font / size / style change.

(fontPickerUpload)      // Event handler for the font upload button click event.
```

##### Available configuration options (for the global configuration):

```javascript
apiKey                  // Your Google API key for the Google Web Fonts API.
```

##### Available control / helper functions (provided by the service):

loadFont(font)          // Loads the given font (family:style) from Web Fonts.

getAllFonts(sort)       // Returns list of Google Fonts with given sort option:
                        // 'alpha' | 'date' | 'popularity' | 'style' | 'trending'

##### Available control / helper functions (provided by the directive):

```javascript
loadFont(font)          // Loads the (font.family:font.style) form Web Fonts.

openDialog()            // Opens the font picker dialog if not already open.
closeDialog()           // Closes the font picker dialog if not already closed.

toggleDialog()          // Toggles the open state of the font picker dialog.
```
