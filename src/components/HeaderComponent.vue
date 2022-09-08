<template>
    <div class="container my-5">
        <h1 class="main-title mb-4">{{ msg }}</h1>
        <div class="search-bar text-center">
            <input v-model="search" @keyup="$emit('search',search)" type="text" class="rounded">
        </div> 
    </div>
</template>

<script>
export default {
    name: "HeaderComponent",
    props: {
        msg: String,
    },
    data() {
        return {
            search: ''
        }
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../styles/general.scss";


</style>
