<template>
    <div id="app">
        <HeaderComponent :msg="title" @search="onSearch" />
        <ListCharactersComponent :search="searchProp" />
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
            searchProp: '',
        };
    },
    components: {
        HeaderComponent,
        ListCharactersComponent,
    },
    methods: {
        onSearch(data) {
            this.searchProp = data
            // console.log('ascolto l\'evento search',data )
        }
    }
};
</script>

<style scoped lang="scss">
</style>
