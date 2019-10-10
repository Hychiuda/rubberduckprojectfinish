<template>
<section id="alphamiddle">

            <div id="headline">List of All Products</div>

                <div id="alphamiddlebox" v-for="context in contexts" v-bind:key="context.id">
                    <div class="middlebox">
                        <div class="category_img"><img src="img/colorduck.png" alt="beautything1" width="200" height="200"></div>
                        <div class="category_text">Data Here</div>
                        <a href="#" class="link_button">BUY</a>
                        </div>
                    
                </div>                                   
        </section>
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

.link_button, .link_button:visited {
  font-family: "Lato", Courier, monospace;
  background-color: #b1e8ed;
  color: #000000;
  margin: -25px 0 0 35px;
  padding: 10px 50px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  border-radius: 25px;
}

.link_button:hover, .link_button:active{
  background-color: #ffd45c;
}

.category_img{
  background-color: #ECEEF0;
  height: 200px;
  width: 200px;
  display: flex;
  flex-direction: row;
}
    
.category_text{
  font-family: "Helvetica", Times, serif;
  height: 100px;
  width: 200px;
  justify-content: center;
  align-content: center;
  display: flex;
  margin-top: 15px;
}

#alphamiddlebox{
  width: 1088px;
  height: 645px;
  align-content: center;
  justify-content: space-between;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
}

#alphamiddle{
  background-color: #ECEEF0;
  width: 100%;
  height: 805px;
}
    
</style>
