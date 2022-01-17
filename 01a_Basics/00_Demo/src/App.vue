<template>
  <!--
  Important: add always a HTML-root element (i.e. div)
  if you are using more than one component
  -->
  <div>
    <MyComponent/>
  </div>

</template>

<script>
/* Import all components */
//import Demo01a from './components/01a_Simple'
//import Demo01b from './components/01b_Title'
// import Demos from './components/02_DataBinding'
//import Demos from './components/03_StylingComponents'
import Demos from './components/04_CSS-Modules'
export default {
  components:{
    MyComponent: Demos
  }
}
</script>

<style lang="scss">
//demo-03
//Import of global-style
@import 'styles/global';
</style>
