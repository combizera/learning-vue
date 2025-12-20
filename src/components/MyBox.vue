<template>
  <div :class="['box', pending]">
    <h1>
      {{ number }}
    </h1>
  </div>
</template>

<script>
  export default {
    name: 'MyBox',
    props: {
      number: {
        type: Number,
        default: 0
      },
      pending: {
        type: String,
        validator: value => ['active', 'inactive'].includes(value),
        default: 'active'
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .box{
    min-width: 50px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 8px;
  }
  .active {
    background-color: #42b983;
  }
  .inactive {
    background-color: lightcoral;
  }
</style>
