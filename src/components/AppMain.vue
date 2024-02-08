<script>

import axios from 'axios';
import CharacterItem from './CharacterItem.vue';

export default {
    name: 'AppMain',
    data() {
        return {
            base_api_url: 'https://rickandmortyapi.com/api/character',
            characters: []
        }
    },
    mounted() {
        axios
            .get(this.base_api_url)
            .then((response) => {
                console.log(response.data);
                console.log(response.data.results); // Characters info

                this.characters = response.data.results

                console.log(this.characters);
            })
    },
    components: {
        CharacterItem
    }
}
</script>
<template>
    <main>
        <div class="container">
            <div class="row">

                <CharacterItem v-for="character in characters" :key="character.id + '_character'" :character="character">
                </CharacterItem>


            </div>
        </div>
    </main>
</template>


<style></style>