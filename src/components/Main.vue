<template>
  <div class="main">
      <disp-comp></disp-comp>
  </div>
</template>

<script>
import DisplayComponent from './DisplayComponent';

export default {
  name: 'Main',

  components: {
    'disp-comp': DisplayComponent,
  },
}
</script>

<style scoped>

</style>