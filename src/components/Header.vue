<template>
    <div class="col col-12" >
        <img src="../assets/spotify.png" alt="">
            <form id="myForm">
                <select 
                v-model="genere" 
                class="form-select form-select-lg-2 " aria-label="Default select example"
                @change="$emit('arrayFiltrato', test)"
                >
                    <option value="all">all</option>
                    <option value="Rock">Rock</option>
                    <option value="Pop">Pop</option>
                    <option value="Jazz">Jazz</option>
                    <option value="Metal">Metal</option>
                </select>
            </form>
    </div>
</template>

<script>
export default {
    nome: "Header",

    props:["status"],
    computed:{
        test: function() {
            const filtroGeneri = this.status.filter(
                (element) => {
                    if(this.genere == "all"){
                        return element;
                    }else{
                        element.genre.includes(this.genere)
                        return  element.genre.includes(this.genere)
                    }
                  
                }
            );
           return filtroGeneri;
        },
    
    },

    
    data: function(){
       return{
           genere:"",
       } 
    },

}
</script>

<style lang="scss" scoped>
//@import '~bootstrap/scss/bootstrap';
    div{
        height: 15vh;
        padding: 15px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #2E3A46;

        img{
            height: 100%;
        }
    }
</style>>