<template>
    <div>
        <nav class="navbar navbar-dark bg-dark d-flex justify-content-between">
            <div class="container-fluid ">
                <img src="../assets/spotify-logo.png" alt="Spotify Logo">

                <div>
                    <select class="form-select" 
                        v-model="selezionaGeneri" 
                        @change="$emit('cambiaGenre', selezionaGeneri)"
                        >
                        <option value="Jazz">Jazz</option>
                        <option value="Rock">Rock</option>
                        <option value="Metal">Metal</option>
                        <option value="Pop">Pop</option>
                    </select>
                </div>

            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'IndexHeader',

    data: function() {
        return {
            selezionaGeneri : '',
        }
    },

    props: {
        generiList: Array,
    },
}
</script>

<style lang="scss" scoped>
    img {
        height: 50px;
    }
</style>