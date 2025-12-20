<template>
  <button @click="$emit('update')">
    {{ title }}
  </button>
</template>

<script>
  export default {
    name: 'MyButton',
    props: {
      title: {
        type: String,
        default: '+1'
      }
    }
  }
</script>

<style>
  button {
    padding: 10px 20px;
    font-size: 20px;
    font-weight: 700;
    border: none;
    border-radius: 5px;
    background-color: #42b983;
    color: white;
    cursor: pointer;
    transition: background-color .25s;
  }
  button:hover {
    background-color: #369870;
  }
</style>