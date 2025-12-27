<template>
  <!-- TASK -->
  <SectionTask />

  <!-- BOX -->
  <SectionBox />

  <!-- COUNTER -->
  <SectionCounter 
    :countValue="countValue" 
    :countStyle="countStyle"
    :countState="countState"
    @change-count="handleCountChange" 
  />
</template>

<script>
  import SectionBox from './components/SectionBox.vue'
  import SectionCounter from './components/SectionCounter.vue';
  import SectionTask from './components/Task/SectionTask.vue';
  
  export default {
    name: 'App',
    components: {
      SectionBox,
      SectionCounter,
      SectionTask,
    },
    data() {
      return {
        countValue: Number(localStorage.getItem('countValue')) || 0
      }
    },
    methods: {
      handleCountChange(action, value = 1) {
        switch(action) {
          case 'increment':
            this.countValue += value
            break
          case 'decrement':
            this.countValue -= value
            break
          case 'reset':
            this.countValue = 0
            break
        }
      }
    },
    computed: {
      countStyle() {
        if (this.countValue < 0) return 'lightcoral';
        if (this.countValue > 0) return 'lightgreen';

        return 'white'
      },
      countState() {
        if (this.countValue < 0) return 'Is negative';
        if (this.countValue > 0) return 'Is positive';
        
        return 'Is zero'
      }
    }, 
    watch: {
      countValue(newValue) {
        // alert(`Count changed from ${oldValue} to ${newValue}`);
        localStorage.setItem('countValue', newValue);
      },
      countStyle(newValue) {
        alert(`Count style changed to ${newValue}`);
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
