# vtitle

Like el-tooltip of Vue.js plugins with Mobile HTML5.

## Usage

### NPM

```
npm i --save vtitle-cli
```

### Element-ui

If your project does not use element-ui,
you need to introduce a separate element-ui package, like this:

```js
import 'vtitle/lib/element-ui';
```

### Global

```js
import Vue from 'vue';
import VTitle from 'vtitle';

Vue.use(VTitle);
```

### Component

```js
import VTitle from 'v-title';

export default {
  components: {
    VTitle
  }
};
```

### Options

#### Modifies

- delay: show delay
- light: use light effect, default: dard
- overflow: use overflow mode
- multiple: use multiple line mode(**need set element's `line-height > offsetHeight`**)

#### Attributes

- title-placement: `String` placement top/right/bottom/left(-start, -end), default: top
- title-delay-time: `Number` show delay time, default: '200'
- title-max-width: `Number` tooltip max width, default: none
- title-class-name: `String` tooltip class name, default: 'v-title'

### Example

```xml
<template>
  <p v-title="title">touch me!</p>

  <!-- modify: light -->
  <p v-title.light="title">touch me!</p>

  <!-- modify: delay -->
  <p v-title.delay="title">touch me!</p>

  <!-- attr: title-delay-time -->
  <p v-title.delay="title" title-delay-time="1000">touch me!</p>

  <!-- attr: title-max-width -->
  <p v-title="title" title-max-width="100">touch me!</p>

  <!-- attr: title-class-name -->
  <p v-title="title" title-class-name="test-class">touch me!</p>

  <!-- modify: overflow -->
  <p v-title.overflow="title">touch me!</p>

  <!-- modify: overflow.multiple -->
  <p v-title.overflow.multiple="title">touch me!</p>

  <!-- attr: title-placement -->
  <p v-title="title" title-placement="bottom">
    top(-start, -end), right(-start, -end), bottom(-start, -end),
    left(-start, -end)，default: top
  </p>
</template>

<script>
import VTitle from 'vtitle';

export default {
  directives: {
    VTitle
  },
  data() {
    return {
      title: 'ABCDEFGABCDEFGABCDEFGABCDEFGABCDEFGABCDEFG',
    };
  }
};
</script>

<style lang="scss">
// custom className
.test-class {
  font-size: 20px;
}
</style>
```
