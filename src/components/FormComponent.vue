<template>
  <div class="form">
      <div>
        {{ person }}
      </div>
  </div>
</template>

<script>
import EventBus from '../event-bus.js';
import axios from '../restClient';

export default {
  mounted(){
    EventBus.$on('person-clicked', this.initializePerson);
  },

  data() {
    return {
      person: {},
    }
  },

  methods: {
    initializePerson(id){
      this.getPerson(id)
        .then(person => {
          console.log(person);
          this.person = person;
        });
    },

    getPerson(id) {
      return axios.get(`/persons/${id}`)
        .then(res => {
          console.log(res.data);
            return res.data;

        })
        .catch(err => {
            console.error('Some shit went wrong with Axios for getting one dude, fam.');
        });
    }
  }
}
</script>

<style scoped>

</style>
