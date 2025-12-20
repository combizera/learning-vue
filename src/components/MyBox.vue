<template>
  <div class="box">
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
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .box{
    width: 50px;
    height: 50px;
    background-color: lightblue;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 8px;
  }
</style>
