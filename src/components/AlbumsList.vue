<template>
    <div>
        <AlbumCard />
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

    created: function (){
        this.getApi();
    },

    methods: {
    getApi () {
        axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result)=> {
        console.log(result);
        })
        .catch((error) =>{
        console.error(error);
        })
        }
    },

    data: function () {
        return {
            albumsList: null,
        }
    }
}
</script>

<style>

</style>