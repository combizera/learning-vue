<template>
  <div class="container">
    <MyBox number="1"/>
    <MyBox number="2"/>
    <MyBox number="3"/>
  </div>
</template>

<script>
import MyBox from './components/MyBox.vue'

export default {
  name: 'App',
  components: {
    MyBox
  }
}
</script>

<style>
  .container {
    display: flex;
    gap: 10px;
    justify-content: center;
    align-items: center;
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
