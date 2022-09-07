<template>
    <div id="app">
        <HeaderComponent :msg="title" />
        <ListCharactersComponent />
    </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import ListCharactersComponent from "./components/ListCharactersComponent.vue";

export default {
    name: "App",
    data() {
        return {
            title: "Rick & Morty",
        };
    },
    components: {
        HeaderComponent,
        ListCharactersComponent,
    },
};
</script>

<style scoped lang="scss">
</style>
