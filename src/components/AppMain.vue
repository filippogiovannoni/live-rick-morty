<script>

import axios from 'axios';

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
    }
}
</script>
<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col-12 col-sm-6 col-lg-4" v-for="character in characters" :key="character.id + 'character'">
                    <div class="card">
                        <img :src="character.image" alt="">
                        <div class="card-info">
                            {{ character.name }}
                            {{ character.species }}
                            {{ character.status }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>


<style></style>