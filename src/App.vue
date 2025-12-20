<template>
  <!-- BOX -->
  <SectionBox />

  <!-- COUNTER -->
  <SectionCounter :count="count" @change-count="handleCountChange" />
</template>

<script>
  import SectionBox from './components/SectionBox.vue'
  import SectionCounter from './components/SectionCounter.vue';
  
  export default {
    name: 'App',
    components: {
      SectionBox,
      SectionCounter,
    },
    data() {
      return {
        count: 0
      }
    },
    methods: {
      handleCountChange(action, value = 1) {
        switch(action) {
          case 'increment':
            this.count += value
            break
          case 'decrement':
            this.count -= value
            break
          case 'reset':
            this.count = 0
            break
        }
      }
    }
  }
</script>

<style>
  html {
    background-color: #2c3e50;
  }
  h2 {
    color: white;
  }
  hr {
    margin: 40px 0;
    opacity: .25;
    border-color: #2c3e50;
  }
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
    margin-top: 60px;
  }
</style>
