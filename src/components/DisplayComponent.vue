<template>
  <div class="form">
      <p>
        Message: {{ formData.msg }}
      </p>
      <p>
        Checked: {{ formData.checked }}
        <input type="checkbox" v-model="formData.checked">
      </p>
      <p>
        {{ fromData.picked }}
        <!-- <input type="radio" name="picked" value="one" v-model="formData.picked">
        <input type="radio" name="picked" value="two" v-model="formData.picked"> -->
      </p>

      <p>
        {{ formData.selected }}
        <!-- <select v-model="">
          <option>one</option>
          <option>two</option>
        </select> -->
      </p>

      <!-- <p>
        <select v-model="formData.multiSelect" multiple>
          <option>one</option>
          <option>two</option>
          <option>three</option>
        </select>
      </p> -->

      <p> {{ $data }}</p>
  </div>
</template>

<script>
export default {
  props: {
    formData: {
      type: Object,
    },
  },
  
  //   data () {
  //       return {
  //       formData : {
  //           msg : 'hi!',
  //           checked  : true,
  //           picked   : 'one',
  //           selected : 'two',
  //           multiSelect: ['one', 'three'],
  //       },
  //   }
  // },
  
}
</script>

<style scoped>

</style>
