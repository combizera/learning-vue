<template>
  <section>
    <h2 :style="{color: countStyle}">
      Counter: {{ count }}
    </h2>
    <div class="container">
      <MyButton 
        title="+1" 
        @update="$emit('change-count', 'increment')" 
      />

      <MyButton 
        title="-1" 
        class="less"
        @update="$emit('change-count', 'decrement')" 
      />
      
      <MyButton 
        title="Reset"
        btnClass="reset"
        @update="$emit('change-count', 'reset')" 
      />
    </div>
    <hr>
  </section>
</template>

<script>
  import MyButton from './MyButton.vue';

  export default {
    name: 'SectionCounter',
    emit: ['change-count'],
    components: {
      MyButton,
    },
    props: {
      count: {
        type: Number,
        default: 0
      },
      countStyle: {
        type: String,
        default: 'white'
      }
    }
  }
</script>