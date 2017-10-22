<template>
  <div class="hello">
    <h1>{{ msg }}</h1>    
    <button v-on:click="GetToDos">Get List</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Home'
    }
  },
  methods: {
    GetToDos () {
      var link = 'http://localhost:59429/api/values'
      axios.get(link)
        .then(function (response) {
          alert('Clicked')
        })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
