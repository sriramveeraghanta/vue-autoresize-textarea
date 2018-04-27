# vue-autoresize-textarea
A autoresizable textarea component build using autosize 

This isn't particularly useful, it's used as a demo for how to publish Vue components to NPM!

## Installation

```js
npm install --save vue-autoresize-textarea
```
or
```js
yarn add vue-autoresize-textarea
```

## Usage
Once installed, it can be used in a template as simply as:

```js
import TextArea from 'vue-autoresize-textarea';
export default {
  data: function () {
    return {
      text: "Hello World"
    }
  },
  components: {
    TextArea
  }
}
```

```html
<TextArea class="yourClassName" v-model="text"></TextArea>
```

## LICENSE
MIT
