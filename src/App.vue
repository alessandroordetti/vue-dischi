<template>
  <div id="app">
    <IndexHeader :generiList="generiList"  @cambiaGenre="aggiornaSelezionaGeneri" />


    <AlbumsList @caricaGeneri ="aggiornaGeneriList" :selezionaGeneri="selezionaGeneri" />

  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue';
import IndexHeader from './components/IndexHeader.vue';

export default {
  name: 'App',
  components: {
    AlbumsList,
    IndexHeader
  },

  data: function(){
    return{
      generiList : [],
      selezionaGeneri:'', 
    }
  },
  
  methods:{
    aggiornaGeneriList(generiList){
      this.generiList = generiList
    },
    aggiornaSelezionaGeneri(selezionaGeneri){
      this.selezionaGeneri = selezionaGeneri
    }
  }

}
</script>

<style lang="scss">
@import '@/style/main-style.scss';
#app {
  background-color: #1e2d3b;
  height: 100vh;
}
</style>