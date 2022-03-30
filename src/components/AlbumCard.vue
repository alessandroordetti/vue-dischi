<template>
    <div>
        <div class="card p-2 text-center">
            <img :src="poster" class="card-img-top" alt="">
            <div class="card-body">
                <h5 class="card-title">{{titolo}}</h5>
                <p class="card-text">{{nome}}</p>
                <p class="card-text">{{genere}}</p>
                <p class="card-text">{{anno}}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',

    props: ['nome', 'genere', 'poster' , 'titolo', 'anno']
}
</script>

<style lang="scss" scoped>

</style>