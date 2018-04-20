<template>
  <div class="main">
    <button @click="editing = !editing">Edit/Save</button>
    <div v-if="editing"><form-comp></form-comp></div>
    <div v-else><disp-comp></disp-comp></div>
  </div>
</template>

<script>
import FormComponent from './FormComponent';
import DisplayComponent from './DisplayComponent';

export default {
  name: 'Main',
  components: {
    'form-comp': FormComponent,
    'disp-comp': DisplayComponent,
  },
  
  data() {
    return {
      editing: "false"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
