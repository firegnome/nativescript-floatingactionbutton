[![npm](https://img.shields.io/npm/v/nativescript-floatingactionbutton.svg)](https://www.npmjs.com/package/nativescript-floatingactionbutton)
[![npm](https://img.shields.io/npm/dt/nativescript-floatingactionbutton.svg?label=npm%20downloads)](https://www.npmjs.com/package/nativescript-floatingactionbutton)
[![Build Status](https://travis-ci.org/bradmartin/nativescript-floatingactionbutton.svg?branch=master)](https://travis-ci.org/bradmartin/nativescript-floatingactionbutton)
[![nStudio Plugin](https://img.shields.io/badge/nStudio-Plugin-blue.svg)](http://nstudio.io)
[![Twitter Follow][twitter-image]][twitter-url]

[twitter-image]: https://img.shields.io/twitter/follow/bradwaynemartin.svg?style=social&label=Follow%20me
[twitter-url]: https://twitter.com/bradwaynemartin

[![PayPal Donate](https://img.shields.io/badge/Donate-PayPal-ff4081.svg)](https://www.paypal.me/bradwayne88)

# NativeScript-FloatingActionButton

XML widget to create the Material Design Floating Action Button for NativeScript apps.

[Material Design Floating Action Button Spec](https://www.google.com/design/spec/components/buttons-floating-action-button.html)

## Installation

`tns plugin add nativescript-floatingactionbutton`

### Screenshot

---

![FAB Android Screenshot](screens/android.png)
![FAB iOS Screenshot](screens/ios.png)

### Multiple FAB/Swipe Animation Support

![FAB Animations](screens/animations.gif)

## Usage

#### XML

##### **NOTE** The sample XML here will position the FAB on top of the ListView. There is no need for absolute positioning due to using a GridLayout row/col settings.

```XML
<Page xmlns="http://schemas.nativescript.org/tns.xsd" loaded="pageLoaded"
      xmlns:FAB="nativescript-floatingactionbutton">
    <ActionBar title="Native FAB" />
    <grid-layout rows="auto, *">
        <list-view row="1" items="{{ users }}">
            <list-view.itemTemplate>
                <label text="{{ name }}" />
            </list-view.itemTemplate>
        </list-view>
            <FAB:fab tap="fabTap"
                     row="1"
                     icon="res://ic_add_white"
                     rippleColor="#f1f1f1"
                     class="fab-button" />
    </grid-layout>
</Page>
```

IMPORTANT NOTE: The fab is on the same **row number** as the listview

---

#### Angular NativeScript

```typescript
import { registerElement } from 'nativescript-angular/element-registry';
registerElement('Fab', () => require('nativescript-floatingactionbutton').Fab);
```

##### HTML

```HTML
<StackLayout>
    <FAB (tap)="fabTap()" icon="res://ic_add_white" rippleColor="#f1f1f1" class="fab-button"></FAB>
</StackLayout>
```

#### NativeScript Vue

```javascript
import Vue from 'nativescript-vue';

Vue.registerElement(
	'Fab',
	() => require('nativescript-floatingactionbutton').Fab
);
```

#### Template

```html
<template>
	<page>
		<grid-layout rows="auto, *">
			<list-view row="1" items="{{ users }}">
				<list-view.itemTemplate>
					<label text="{{ name }}" textWrap="true" />
				</list-view.itemTemplate>
			</list-view>
			<fab
				@tap="fabTap"
				row="1"
				icon="res://ic_add_white"
				rippleColor="#f1f1f1"
				class="fab-button"
			></fab>
		</grid-layout>
	</page>
</template>
```

#### CSS

Recommended CSS styles.

```css
.fab-button {
	height: 70;
	width: 70; /// this is required on iOS - Android does not require width so you might need to adjust styles
	margin: 15;
	background-color: #ff4081;
	horizontal-align: right;
	vertical-align: bottom;
}
```

---

#### JS

```JS
exports.fabTap = function(args) {
    console.log('tapped');
}
```

---

## API

| Property              | Android | iOS | Description                                                                    | Note                                                                                                 |
| --------------------- | ------- | --- | ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| backgroundColor       | X       | X   | Sets the background color of the button                                        |
| icon                  | X       | X   | Supports the same image source options that NativeScript images support        | Required on android                                                                                  |
| rippleColor           | X       |     | Ripple color on lollipop devices, it will fill the FAB on pre-lollipop devices | None                                                                                                 |
| hideOnSwipeOfView     | X       | X   | Directs the fab to animate itself in and out on scroll                         | Pass it the name of the view to monitor for a scroll event example: hideOnSwipeOfView="userListView" |
| hideAnimationDuration | X       | X   | How many milliseconds it takes for the button to hide.                         | Default if not set: 300ms                                                                            |
| swipeAnimation        | X       | X   | slideDown, slideUp, slideLeft, slideRight, scale                               | Default is slideDown                                                                                 |

## iOS Notes

- We're using [MNFloatingActionButton](http://cocoapods.org/pods/MNFloatingActionButton) by [Matt Nydam](https://github.com/mattnydam)
- Width\Height are requried properties
- icon is a required property, if left as empty string default will be shown

### [Changelog](./CHANGELOG.md)

### Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

| [<img src="https://avatars1.githubusercontent.com/u/6006148?s=100&v=4" width="100px;"/><br /><sub>Brad Martin</sub>](https://github.com/bradmartin) | [<img src="https://avatars1.githubusercontent.com/u/1542376?s=100&v=4" width="100px;"/><br /><sub>Steve McNiven-Scott</sub>](https://github.com/sitefinitysteve) | [<img src="https://avatars3.githubusercontent.com/u/850871?s=100&v=4" width="100px;"/><br /><sub>Nathanael Anderson</sub>](https://github.com/NathanaelA) | [<img src="https://avatars3.githubusercontent.com/u/1100522?s=100&v=4" width="100px;"/><br /><sub>Gabriel Marinho</sub>](https://github.com/gabrielbiga) |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |


| [<img src="https://avatars1.githubusercontent.com/u/4092076?s=100&v=4" width="100px;"/><br /><sub>Alexander Vakrilov</sub>](https://github.com/vakrilov) | [<img src="https://avatars1.githubusercontent.com/u/8123916?s=100&v=4" width="100px;"/><br /><sub>Lázaro Danillo Menezes</sub>](https://github.com/lazaromenezes) | [<img src="https://avatars0.githubusercontent.com/u/8638243?s=100&v=4" width="100px;"/><br /><sub>Jofferson Ramirez Tiquez</sub>](https://github.com/jofftiquez) | [<img src="https://avatars3.githubusercontent.com/u/9256365?s=100&v=4" width="100px;"/><br /><sub>Ravi</sub>](https://github.com/dlucidone) |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |


| [<img src="https://avatars3.githubusercontent.com/u/13824510?s=100&v=4" width="100px;"/><br /><sub>Samuel Ikechukwu</sub>](https://github.com/holymp2006) | [<img src="https://avatars2.githubusercontent.com/u/7893485?s=100&v=4" width="100px;"/><br /><sub>Stanimira Vlaeva</sub>](https://github.com/sis0k0) |     |     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- |


<!-- ALL-CONTRIBUTORS-LIST:END -->
