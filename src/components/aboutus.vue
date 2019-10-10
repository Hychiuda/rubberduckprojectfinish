<template>

</template>

<script>
import axios from 'axios' 

export default {
  name: 'app',
    mounted() {
      this.loadContent()
    },
  data: () => {
    return {
      contexts: []
    }
  },
  methods: {
    loadContent: function() {
      axios.get('https://rubberduckshop.azurewebsites.net/api/duck').then(response => (this.contexts = response.data))
    }
  }
}

</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
