<template>
  <div id="app">
    <toolbar v-on:scroll-down="scrollToClass"></toolbar>
    <img class="logo" alt="acaMEDia logo" src="./assets/logo.png">
    <home></home>
  </div>
</template>

<script>

  import Home from "./Containers/Home";
  const scroller = {
    methods: {
      scrollToClass(className) {
        // Get the first element with the given class name
        var el = this.$el.getElementsByClassName(className)[0];
        // Get the bounding rectangle so we can get the element position position
        let rect = el.getBoundingClientRect()
        // Scroll to the element (using x and y axis)
        window.scrollTo(rect.left, rect.top)
      }
    }
  };
  import Toolbar from './components/toolbar.vue'
  export default {
    name: 'app',
    mixins: [scroller],
    components: {
      Home,
      Toolbar
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
