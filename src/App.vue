<template>
  <section>
    <h2>
      My Boxes
    </h2>
    <div class="container">
      <MyBox />
      <MyBox number=1 pending="inactive"/>
      <MyBox number=2 />
      <MyBox number=3 />
    </div>
    <hr>
  </section>
  
  <section>
    <h2>
      Button
    </h2>
    <div class="container">
      <MyButton 
        title="+1" 
        @update="incrementCount" 
      />
      <MyButton 
        title="-1" 
        @update="decrementCount" 
      />
      <MyButton 
        title="Reset" 
        @update="resetCount" 
      />
    </div>
    <p class="counter">
      Counter: {{ count }}
    </p>
    <hr>
  </section>
</template>

<script>
  import MyBox from './components/MyBox.vue'
  import MyButton from './components/MyButton.vue'
  
  export default {
    name: 'App',
    components: {
      MyBox,
      MyButton
    },
    data() {
      return {
        count: 0
      }
    },
    methods: {
      incrementCount() {
        this.count ++
      },
      decrementCount() {
        this.count --
      },
      resetCount() {
        this.count = 0
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
  .counter {
    color: white;
    font-size: 24px;
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
