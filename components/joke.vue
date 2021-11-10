<template>
    <div class="joke"> 
        <!-- this will display the data fetched in the jokes array -->
        <p>{{joke}}</p>

    </div>
</template>

<script lang="ts">

export default {
    name: 'Joke',
    props: ['joke', 'id']

}
</script>

<style scoped>

.joke {
    padding: 1rem;
    border: 1px dotten #ccc;
    margin: 1rem 0;
}
</style>
