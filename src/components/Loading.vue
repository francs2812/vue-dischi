<template>
  <div>
       <img src="../assets/spotify.png" alt="">
       <h1>Caricamento </h1>
  </div>
</template>

<script>
export default {
    name:"Loading",

}
</script>

<style lang="scss" scoped>

    div {
        padding: 150px;
        font-size: 50px;
        color: white;
        text-align: center;

        img{
           width: 150px;
        }
        h1::after {
           content: ".";
           animation-name: example;
            animation-duration: 2s;
            animation-direction: alternate;
            animation-iteration-count: infinite;
        }
        // h1::after {
        // content: "...";
        // width: 10px;
        // height: 10px;
        // color: red;
        // }
    }

    @keyframes example {
        50% {
            //color:yellow
            content: "..";
            
        }
        
        100% {
            content: "...";
            //color: red;
            
        }
    }
</style>