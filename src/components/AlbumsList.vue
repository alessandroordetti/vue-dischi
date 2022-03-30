<template>
    <div class="container">
        <div class="row">
            <div class="col-6 col-md-2 mx-2 my-2" v-for="(element, index) in albumsListArray" :key=index>
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

    data: function () {
        return {
            albumsListArray: null,
        }
    },

    created: function (){
        this.getApi();
    },

    methods: {
    getApi () {
        axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result)=> {
        this.albumsListArray = result.data.response;
        console.log(result);
        })
        .catch((error) =>{
        console.error(error);
        })
        }
    },
}
</script>

<style lang="scss" scoped>

</style>