<template>
  <div class="container">
      <div class="row">
        <div 
        class="col-2 mx-1 text-center"
        v-for="(stato, index) in status"
        :key="index"
        >
            <img :src="stato.poster" alt="image_album">
            <h1> {{stato.title}} </h1>
            <p> {{stato.author}} <br> {{stato.year}}</p>
        </div>

      </div>
  </div>
</template>

<script>
//import axios from 'axios';
export default {
    name:"Main",
    props:{
        status,
        },
    data: function() {
        return {
        }
    },


}
</script>

<style lang="scss" scoped>
.row {
    display: flex;
    justify-content: center;
}

    .row div {
        margin-top: 20px;
        background-color: #2E3A46;

        img{
            width:100%;
            margin-top: 15px;
        }
        h1 {
            font-size: 24px;
            font-weight: 700;
            margin: 20px 0;
            cursor: pointer;
            text-transform: uppercase;
            color: white;
        }
        p {
            font-size: 18px;
            font-weight: 600;
            color: #808080;
        }
    }
</style>