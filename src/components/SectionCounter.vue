<template>
  <section>
    <h2 :style="{color: countStyle}">
      Counter: {{ countValue }}
    </h2>
    <div class="container">
      <MyButton 
        title="+1" 
        @update="$emit('change-count', 'increment')" 
      />

      <MyButton 
        title="-1" 
        class="less"
        :disabled="!canDecrement"
        @update="$emit('change-count', 'decrement')" 
      />
      
      <MyButton 
        title="Reset"
        btnClass="reset"
        :disabled="!canReset"
        @update="$emit('change-count', 'reset')" 
      />
    </div>

    <p :style="{color: countStyle}">
      {{ countState }}
    </p>
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
      countValue: {
        type: Number,
        required: true,
        default: 0
      },
      countStyle: {
        type: String,
        default: 'white'
      },
      countState: {
        type: String,
        default: 'Is zero'
      }
    },
    computed: {
      canDecrement() {
        return this.countValue > -10;
      },
      canReset() {
        return this.countValue !== 0;
      }
    }
  }
</script>

<style scoped>
  p {
    color: white;
    font-size: 18px;
  }
</style>