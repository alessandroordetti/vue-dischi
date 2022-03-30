<template>
  <div id="app">
    <h1 class="text-danger">Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit, quo id obcaecati odio veniam sit quis ducimus aliquam similique natus, fugiat architecto odit dolorem a maiores ea sed? Quis, quasi?</h1>
    <AlbumsList />
  </div>
</template>

<script>
import AlbumsList from './components/AlbumsList.vue'

export default {
  name: 'App',
  components: {
    AlbumsList,
  }
}
</script>

<style lang="scss">
@import '@/style/main-style.scss';


</style>
