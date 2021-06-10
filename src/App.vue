<template>
  <div id="app">
    <div v-if="loading">
      <Loading />
    </div>
    <div v-else>

      <Header :status="dischi" @arrayFiltrato="arrayFiltrat"/>
      <Main   :status="dischi"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Loading from './components/Loading.vue'

export default {
  name: 'App',
  components: {
   Header,
   Main,
   Loading
  },
  data: function() {
    return {
    loading: true,
    url: "https://flynn.boolean.careers/exercises/api/array/music",
    dischi:[],
    dischi2:[]
    //arrayFiltrato:[]
    }


  },
  created(){
        axios
            .get(this.url)
            .then( 
                (response) => {
            // handle success
            //console.log(response.data.response);
            this.dischi = response.data.response;
            setTimeout( () => {
            this.loading = 0
            }, 0);
            }
            )
            .catch();
            },
  methods: {
    arrayFiltrat: function(array){
    return this.dischi2 = array;
    //return console.log(array);
     
    }
  },



  
}
</script>

<style lang="scss">
  @import '~bootstrap/scss/bootstrap';
   *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    }
    #app {
      width: 100%;
      height: 100%;
      background-color: #1e2d3b;
      padding-bottom: 50px;
    }
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500;600;700&family=Roboto:wght@500;700&display=swap');

</style>
