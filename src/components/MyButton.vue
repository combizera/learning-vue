<template>
  <button :class="['button', btnClass]" @click="$emit('update')">
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
      },
      btnClass: {
        type: String,
        validator: value => ['more', 'less'].includes(value),
        default: 'more'
      }
    }
  }
</script>

<style scoped>
  .button {
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
  .button:hover {
    background-color: #369870;
  }
  .less {
    background-color: lightcoral;
  }
  .less:hover {
    background-color: #d46a6a;
  }
  .reset {
    background-color: gray;
  }
  .reset:hover {
    background-color: #5c5c5c;
  }
</style>