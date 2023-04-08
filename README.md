# vue-infinite-loading
****
🫂 **Credit**
\
This is a fork of https://github.com/PeachScript/vue-infinite-loading, credits to @PeachScript
\
This fork is based on this problem and solution: https://github.com/PeachScript/vue-infinite-loading/issues/322, credits to @muhammad-sayed-mahdy
\
And credits for myself, for updating the dev template, testing the solution, and working on this fork 😁
****

✅ **Maintained**
\
As I see the original repository is unmaintained, so I am open for pull requests and issues about the package.
****
📔 **Newer documentation**
\
I made a new beginner-friendly documentation for the package, hope it helps :)
****

# Documentation
## ☁️ **Installation**
### **With npm**
```
npm install --save git+https://github.com/vrolandd/vue-infinite-loading.git#master
```

... more sources will be added later

### **Without npm,**
you can just download the .js file and import it:

```html
<script src="/assets/js/vue-infinite-loading.js"></script>
```
[Download latest from GitHub](https://raw.githubusercontent.com/vrolandd/vue-infinite-loading/master/dist/vue-infinite-loading.js)


## ⬅️ **Import**
### 🧩 Import as a **component**
```html
<template>
    <div class="myApp">
        <infinite-loading ...></infinite-loading>
    </div>
</template>

<script>
import InfiniteLoading from 'vue-infinite-loading';

export default {
    components: {
        InfiniteLoading,
    },
};
</script>
```

## 🔌 Import using **plugin API**:
If you want to configure default options, you can register this plugin through the `use` API of Vue.js:
```js
// main.js or index.js
import InfiniteLoading from 'vue-infinite-loading';

Vue.use(InfiniteLoading, { /* options */ });
```
If you use the plugin API, the **`InfiniteLoading`** component will be registered as a global component just like when including it with the `<script>` tag, but you won't need to re-register it through the `components` property in your own components.

---
## <img src="https://upload.wikimedia.org/wikipedia/commons/a/ae/Nuxt_logo.svg" height="17"> **Use with nuxt 2**
`/plugins/infiniteloading.js`
```js
import Vue from 'vue'
import InfiniteLoading from 'vue-infinite-loading'
Vue.component('infinite-loading', InfiniteLoading)
```

`nuxt.config.js`
```js
export default {
    ...
    plugins: [
        { src: '@/plugins/infiniteloading', ssr: false }
    ]
    ...
}
```

`/pages/example.vue`
```html
<template>
    <div class="listContainer">
        <span v-for="Item in items" v-bind:key="Item.id"></span>
        <infinite-loading ...>
            
        </infinite-loading>
    </div>
</template>

```


## 🔃 **Scroll directions**
### **Bottom** (default):
`/pages/example.vue`
```html
<template>
    <div class="listContainer">
        <span v-for="Item in items" v-bind:key="Item.id"></span>
        <!-- Scrolling down; if the infinite-loading component is visible or in the given distance from the bottom, loading will be started -->
        <infinite-loading direction="bottom" ...>
            
        </infinite-loading>
    </div>
</template>
```

### **Top**:
`/pages/example.vue`
```html
<template>
    <div class="listContainer">
        <infinite-loading direction="top" ...>
            
        </infinite-loading>

        <!-- Scrolling up; if the infinite-loading component is visible or in the given distance from the top, loading will be started -->

        <span v-for="Item in items" v-bind:key="Item.id"></span>
    </div>
</template>
```

### **Reverse-top** (🧩 bonus):
`/pages/example.vue`
```html
<template>
    <div class="listContainer" style="flex-direction: column-reverse;">
        <!-- Scrolling up; if the infinite-loading component is visible or in the given distance from the top, loading will be started -->
        <span v-for="Item in items" v-bind:key="Item.id"></span>

        <infinite-loading direction="reverse-top" ...>
            
        </infinite-loading>
        <!-- The infinite-loading component is at the bottom, because the flex-direction: column; rule will make the layout reversed. Since the component needs to be at the top, we place it to the bottom of the code.  -->
    </div>
</template>
```
---

## 🪟 **Defining scrollable container**
```html
<template>
    <div class="listContainer">
        <div class="scrollContainer">
            <infinite-loading
              force-use-infinite-wrapper=".scrollContainer">
            </infinite-loading>
        </div>
    </div>
</template>
```
The `force-use-infinite-wrapper` must have a valid and unique **element selector**, like in CSS:
### **Examples**
### Selecting an element by class
```html
<div class="scrollContainer">
    <infinite-loading
      force-use-infinite-wrapper=".scrollContainer">
    </infinite-loading>
</div>
```
### Selecting an element by id
```html
<div id="scrollable">
    <infinite-loading
      force-use-infinite-wrapper="#scrollable">
    </infinite-loading>
</div>
```

### Selecting an element by classes accurately
```html
<div class="scrollContainer mainScroll">
    <infinite-loading
      force-use-infinite-wrapper=".scrollContainer.mainScroll">
    </infinite-loading>

    <div class="scrollContainer">
        <div class="mainScroll">
          
        </div>
    </div>
</div>
```
___
Thats's all for now,\
you can see https://peachscript.github.io/vue-infinite-loading/ for more examples and options.

---

# **License**

The MIT License (MIT)

Copyright (c) 2016-present PeachScript<scdzwyxst@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
