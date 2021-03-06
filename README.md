# vue-event-calendar

> A simple events calendar for Vue2, no dependencies except Vue2. responsive & mobile first.
> [Live Demo Here](http://geoffzhu.cn/vue-event-calendar/)

![](http://o80ronwlu.bkt.clouddn.com/vue-event-calendar.gif)

[![npm version](https://img.shields.io/npm/v/vue-event-calendar.svg)](https://www.npmjs.com/package/vue-event-calendar)

## Requirements
- vue: ^2.0.0

## Usage
#### install

``` sh
 npm install vue-event-calendar --save
```

#### main.js

```javascript
import vueEventCalendar from 'vue-event-calendar'
Vue.use(vueEventCalendar, {locale: 'en'}) //locale can be 'zh' or 'en'
```

#### file.vue

```vue
<template>
  <vue-event-calendar :events="demoEvents"></vue-event-calendar>
</template>

<script>
export default {
  data () {
    return {
      demoEvents: [{
        date: '2016/12/15',
        title: 'eat',
        desc: 'longlonglong description'
      },{
        date: '2016/11/12',
        title: 'this is a title'
      }]
    }
  }
}
</script>
```
## Customization
If you want customization event template. required Vue: ^2.1.0. Because I use new feature(Scoped Slots) of ^2.1.0

### color

```javascript
//When Vue.use, you can give a color
Vue.use(vueEventCalendar, {locale: 'en', color: '#4fc08d'})
```

### event template
```vue
<template>
  <vue-event-calendar :events="demoEvents">
      <template scope="props">
        <div v-for="(event, index) in props.showEvents" class="event-item">
          <!-- In here do whatever you want, make you owner event template -->
          {{event}}
        </div>
      </template>
    </vue-event-calendar>
</template>

<script>
export default {
  data () {
    return {
      demoEvents: [{
        date: '2016/12/15',
        title: 'eat',
        desc: 'longlonglong description'
      },{
        date: '2016/11/12',
        title: 'this is a title'
      }]
    }
  }
}
</script>
```

## Api
```javascript
// NextMonth
this.$EventCalendar.nextMonth()
```
```javascript
// PreMonth
this.$EventCalendar.preMonth()
```
```javascript
//ToDate
this.$EventCalendar.toDate('2016/11/12')
```
More in [Demo Folder](https://github.com/GeoffZhu/vue-event-calendar/tree/master/demo)

## Develop
```
npm run dev  //develop
npm run build //production
```


