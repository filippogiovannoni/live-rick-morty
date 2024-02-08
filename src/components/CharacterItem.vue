<script>
export default {
    name: 'CharacterItem',
    data() {
        return {

        }
    },
    props: {
        character: Object
    }
}
</script>
<template>
    <div class="col-12 col-sm-6 col-lg-4">
        <div class="card">
            <img :src="character.image" alt="">
            <div class="card-info">
                {{ character.name }}
                {{ character.species }}
                {{ character.status }}
            </div>
        </div>
    </div>
</template>


<style>
.card {
    background-color: white;
    transition: all 1s;

    &:hover {
        filter: drop-shadow(0 0 15px #5126c7ad);
        scale: 1.03;
    }

    & img {
        width: 100%;
    }
}

.card-info {
    padding: 0.5rem;
}
</style>