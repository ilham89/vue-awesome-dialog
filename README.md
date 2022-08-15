# vue-awesome-dialog

[![](https://data.jsdelivr.com/v1/package/npm/vue-awesome-dialog/badge)](https://www.jsdelivr.com/package/npm/vue-awesome-dialog)

A awesome dialog component for Vue3

## Installation

**NPM**

```
npm i vue-awesome-dialog
```

**YARN**

```
yarn add vue-awesome-dialog
```

**CDN**

```
https://www.jsdelivr.com/package/npm/vue-awesome-dialog
```

## Getting Started

To install it globally.

```javascript
import { createApp } from "vue";
import App from "./App.vue";
import VueAwesomeDialog from "vue-awesome-dialog";

createApp(App).use(VueAwesomeDialog).mount("#app");
```

```html
<template>
    <div>
        <vue-awesome-dialog />
    </div>
</template>
```

If not globally, you can also import the individual components locally.

```javascript
<script>
import VueAwesomeDialog from "vue-awesome-dialog";
export default {
  components: {
    VueAwesomeDialog,
  },
};
</script>
```

```html
<template>
    <div>
        <vue-awesome-dialog />
    </div>
</template>
```

### Events

| Name  | Usage    | Description              |
| ----- | -------- | ------------------------ |
| close | `@close` | Emitted for close dialog |
| save  | `@save`  | Emitted for save dialog  |

### Slots

| Name   | Description                  |
| ------ | ---------------------------- |
| header | Slot for custom header       |
| bosy   | Slot for custom body content |

### Example

```javascript
<button @click="show = true">show</button>
<vue-awesome-dialog v-show="show" @close="show = false" @save="add">
    <template v-slot:header>Custom Title</template>
    <template v-slot:body>
        It is a long established fact that a reader will be distracted
        by the readable content of a page when looking at its layout.
    </template>
</vue-awesome-dialog>
```
