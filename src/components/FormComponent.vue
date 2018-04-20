<template>
  <div class="form">
      <p>
        <input type="text" v-model="formData.msg" lazy>
      </p>
      <p>
        <input type="checkbox" v-model="formData.checked">
      </p>
      <p>
        <input type="radio" name="picked" value="one" v-model="formData.picked">
        <input type="radio" name="picked" value="two" v-model="formData.picked">
      </p>

      <p>
        <select v-model="formData.selected">
          <option>one</option>
          <option>two</option>
        </select>
      </p>

      <p>
        <select v-model="formData.multiSelect" multiple>
          <option>one</option>
          <option>two</option>
          <option>three</option>
        </select>
      </p>

      <p> {{ $data }}</p>
  </div>
</template>

<script>
export default {
    data () {
        return {
        formData : {
            msg : 'hi!',
            checked  : true,
            picked   : 'one',
            selected : 'two',
            multiSelect: ['one', 'three'],
        },
    }
  },
  
}
</script>

<style scoped>

</style>
