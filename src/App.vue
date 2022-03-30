<template>
  <div id="app">
    <IndexHeader />


    <AlbumsList />

  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue'
import IndexHeader from './components/IndexHeader.vue';

export default {
  name: 'App',
  components: {
    AlbumsList,
    IndexHeader
  },


}


</script>

<style lang="scss">
@import '@/style/main-style.scss';

#app {
  background-color: #1e2d3b;
}

</style>
