#### chrome://app-service-internals

- Image size: 128×128

- Button styles: User-Agent default (Default)

- Font styles:

```css
h3 {
    display: block;
    font-size: 1.17em;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}
```
- Script references (HTML):

```html
<script type="module" src="app_service_internals.js"></script>
```

- Script references (JS):

```js
import {PolymerElement} from "chrome://resources/polymer/v3_0/polymer/polymer_bundled.min.js"; // chrome://resources/polymer/v3_0/polymer/polymer_bundled.min.js
import {getTemplate} from "./app_service_internals.html.js"; // chrome://app-service-internals/app_service_internals.html.js
import {AppServiceInternalsPageHandler} from "./app_service_internals.mojom-webui.js"; // chrome://app-service-internals/app_service_internals.mojom-webui.js
```

- Replication: Make your own custom elements using the DOM `customElements.define()` API like so:

```javascript
customElements.define('app-service-internals', class extends HTMLElement {
    // constructor() { ... }
    // ...
});
```

- Then style it like so:

- From `chrome://resources/css/roboto.css`:

```css
/* Copyright 2015 The Chromium Authors
    * Use of this source code is governed by a BSD-style license that can be
    * found in the LICENSE file. */

@font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 400;
    src: local('Roboto'), local('Roboto-Regular'),
        url(//resources/roboto/roboto-regular.woff2) format('woff2');
}

@font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 500;
    src: local('Roboto Medium'), local('Roboto-Medium'),
        url(//resources/roboto/roboto-medium.woff2) format('woff2');
}

@font-face {
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    src: local('Roboto Bold'), local('Roboto-Bold'),
        url(//resources/roboto/roboto-bold.woff2) format('woff2');
}
```

- From `chrome://resources/css/text_defaults_md.css`:

```css
/* Copyright 2015 The Chromium Authors
    * Use of this source code is governed by a BSD-style license that can be
    * found in the LICENSE file. */

/* This file is dynamically processed by a C++ data source handler to fill in
    * some per-platform/locale styles that dramatically alter the page. This is
    * done to reduce flicker, as JS may not run before the page is rendered.
    *
    * There are two ways to include this stylesheet:
    * 1. via its chrome://resources/ URL in HTML, i.e.:
    *
    *   <link rel="stylesheet" href="chrome://resources/css/text_defaults_md.css">
    *
    * 2. via the webui::AppendWebUICSSTextDefaultsMd() method to directly append it
    * to an HTML string.
    * Otherwise its placeholders won't be expanded. */


@import url(//resources/css/roboto.css);


body {
    font-family: Roboto, "Noto Sans", Arial, sans-serif;
    font-size: 81.25%;
}

button {
    font-family: Roboto, "Noto Sans", Arial, sans-serif;
}
```