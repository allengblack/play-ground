<template>
  <div class="main">
      <div v-if="inEditMode">
        <form-component></form-component>
      </div>

      <div v-else class="form">
          <table>
              <tr>
                  <th>id</th>
                  <th>Name</th>
                  <th>Email</th>
                  <th>Profession</th>
                  <th>Married?</th>
              </tr>

              <tr v-for="person in allPeople" :key="person.id" @click="clickPerson(person.id)">
                  <td>{{ person.id }}</td>
                  <td>{{ person.name }}</td>
                  <td>{{ person.email }}</td>
                  <td>{{ person.profession }}</td>
                  <td>{{ person.married }}</td>
              </tr>
          </table>
      </div>
  </div>
</template>

<script>
import axios from '../restClient';
import EventBus from '../event-bus.js';
import FormComponent from './FormComponent.vue';

export default {
  components: {
      'form-component': FormComponent
  },
  
  created() {
      this.getPeople().then(persons => {
          this.allPeople = persons;
      });
  },

  data() {
      return {
        inEditMode: false,
        allPeople: {},
      }
  },

  methods: {
    getPeople() {
      return axios.get('/persons')
        .then(res => {
            return res.data;
        })
        .catch(err => {
            console.error('Some shit went wrong with Axios, fam.');
        });
    },
    
    clickPerson(id) {
      this.inEditMode = true;
      EventBus.$emit('person-clicked', id);
      console.log('I got emitted.', id);
    }
  }
}
</script>

<style scoped>
  table {
    width: 80%;
    margin: 0 auto 20px;
    font-family: arial, sans-serif;
    border-collapse: collapse;
  }

  td, th {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
  }

  tr:hover{
    background-color: cyan;
    cursor: pointer;
  }

  th {
    background-color: #fff;
    cursor: default;
  }
</style>
