<template>
    <div class="container">
        <div>
            {{ counter }}
            <b @click="counter++">
                +
            </b>
        </div>
        <div class="row g-4">
            <div
                v-for="character of filteredCharacters"
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
    props: {
        search: {
            type: String,
            default: '',
        }
    },
    data() {
        return {
            listCharacters: [],
            counter: 0
            // search: 'alex'
        };
    },
    computed: {
        filteredCharacters() {
           console.log('filtra')
            return this.listCharacters.filter((el) => {
                const name = el.name.toLowerCase()
                const find = this.search.toLowerCase()

                if(name.includes(find)) {
                    return true
                }

                return false

            })
        }
    },
    methods: {
        // filteredCharacters() {
        //     console.log('filtra')
        //     return this.listCharacters.filter((el) => {
        //         const name = el.name.toLowerCase()
        //         const find = this.search.toLowerCase()

        //         if(name.includes(find)) {
        //             return true
        //         }

        //         return false

        //     })
        // }
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
