<template>
    <div class="container p-4">
        <div class="row">
            <div class="" v-for="(element, index) in filtradischi" :key=index>
                <AlbumCard 
                :nome="element.author"
                :genere="element.genre"
                :poster="element.poster"
                :titolo="element.title"
                :anno="element.year"
                />
            </div>
        </div>
    </div>

</template>

<script>
import axios from "axios";
import AlbumCard from "./AlbumCard.vue"

export default {
    name: 'AlbumsList',
    components: {
        AlbumCard
    },

props : ['selezionaGeneri'],
    
data:function(){
    return{
        IndexMainDiscs: [],      
        generiList : [],      
    }
},
    
computed:{
    
    filtradischi(){
    if(this.selezionaGeneri === ''){
        console.log(this.selezionaGeneri)
        return this.generiList
        
    }
        return this.generiList.filter(
        (element) => element.genre === this.selezionaGeneri)

    }
},

created(){
    
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")            
    .then((risultato)=>{ 
    
        console.log(risultato.data)
        this.generiList = risultato.data.response;
        this.generiList.forEach((element) => {
        if(!this.IndexMainDiscs.includes(element.genre)){
            this.IndexMainDiscs.push(element.genre)
        }
        });
        this.$emit('caricaGeneri', this.IndexMainDiscs)
    })
      .catch((errore) =>{                   // se non dovesse avveninire comunicheremo un determinato errore
        console.log(errore)
    })
    }
    
}
</script>

<style lang="scss" scoped>
    .row > div {
        width: calc(100% / 5);
        margin-bottom: 1rem;
    }

    .container {
        background-color: 1e2d3b;
    }
</style>