<template>
    <div class="card">
        <img class="card-img-top" :src="info.image" alt="Card image cap" />
        <div class="card-body">
            <h5 class="card-title">{{ info.name }}</h5>
            <p class="card-text">
                {{ info.species }} <br />
                {{ info.origin }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: "CharacterComponent",
    props: {
        info: Object,
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../styles/card";
</style>
