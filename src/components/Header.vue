<template>
    <div class="col col-12" >
        <img src="../assets/spotify.png" alt="">
            <form id="myForm">
                <select v-model="genere" action="/action_page.php" class="form-select form-select-lg-2 " aria-label="Default select example">
                    <option value="Rock">Rock</option>
                    <option value="Pop">Pop</option>
                    <option value="Jazz">Jazz</option>
                    <option value="Metal">Metal</option>
                </select>
            </form>
            <h1 ></h1>
            <!-- <br><br> -->
            <input type="submit" value="Submit"
            @keyup="$emit('arrayFiltrato', generiFiltrati)"
            >
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
                  element.genre.includes(this.genere)
                 return  element.genre.includes(this.genere)
                }
            );
            return this.generiFiltrati = filtroGeneri ;
        }
    },
    data: function(){
       return{
           genere:"",
           generiFiltrati: '',
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