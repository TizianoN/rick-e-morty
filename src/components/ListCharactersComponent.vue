<template>
    <div class="container">
        <div class="row g-4">
            <div
                v-for="character of listCharacters"
                :key="character.id"
                class="col-3"
            >
                <CharacterComponent :info="character" />
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import CharacterComponent from "./CharacterComponent.vue";

export default {
    name: "ListCharactersComponent",
    data() {
        return {
            listCharacters: [],
        };
    },
    created() {
        axios
            .get("https://api.sampleapis.com/rickandmorty/characters")
            .then((res) => {
                console.log(res.data);
                this.listCharacters = res.data;
            })
            .catch((err) => {
                console.log("Error:", err);
            })
            .finally(() => {
                // console.log("Finito");
            });
    },
    components: {
        CharacterComponent,
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../styles/general.scss";
</style>
