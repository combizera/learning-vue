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
</template>

<script>
  import MyBox from './MyBox.vue';

  export default {
    name: 'SectionBox',
    components: {
      MyBox,
    },
  }
</script>