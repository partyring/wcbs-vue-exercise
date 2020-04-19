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
          <td>{{ country.name }}</td>
          <td>{{ country.code }}</td>
          <td><button @click="removeCountry(index)">Remove Country</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import countries from './countries.json';
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  methods: {
    removeCountry: function(index) {
      // Remove country from UI list
      this.$delete(this.myCountries, index)
      // TODO: Remove from JSON data

    }
  },
  data(){
    return {
        myCountries: countries
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
