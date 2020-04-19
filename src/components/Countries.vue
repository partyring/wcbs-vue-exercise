<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <table>
      <thead>
        <tr>
          <th>Country Name</th>
          <th>Country Code</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(country, index) in myCountries" :key="country.code">

        <template v-if="index === currentlyBeingEdited">
          <td><textarea v-model="country.name"></textarea></td>
          <td><textarea v-model="country.code"></textarea></td>
          <button @click="saveCountry(index, country.name, country.code)">Save Country</button>
          <td><button @click="removeCountry(index)">Remove Country</button></td>
        </template>
        <template v-else>
          <td>{{ country.name }}</td>
          <td>{{ country.code }}</td>
          <td><button @click="editCountry(index)">Edit Country</button></td>
          <td><button @click="removeCountry(index)">Remove Country</button></td>
        </template>

        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import countries from '../files/countries.json';

export default {
  name: 'Countries',
  props: {
    msg: String,
  },
  methods: {
    removeCountry: function(index) {
      // Remove country from UI list
      this.$delete(this.myCountries, index)
    },
    editCountry: function(index) {
      this.currentlyBeingEdited = index;
    },
    saveCountry: function(index, name, code) {
      this.$set(this.myCountries, index, {'code': code,'name': name})

      this.currentlyBeingEdited = {}
    }
  },
  data(){ 
    return {
        myCountries: countries,
        currentlyBeingEdited: {

        }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
