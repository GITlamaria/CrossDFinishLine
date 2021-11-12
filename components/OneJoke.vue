<template>
<nuxt-link :to="'jokes/' + id "> <!-- will make each joke a link -->
    <div class="joke">
        <p>
            {{ joke }}
        </p>
    </div>
</nuxt-link>

</template>

<script>

export default {
    name: 'OneJoke',
    props: ['joke', 'id']
}
</script>

<style scoped>

.joke {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
}
</style>