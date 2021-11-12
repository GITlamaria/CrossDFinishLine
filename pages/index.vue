<template>
  <Home />

</template>

<script>
import Home from '../pages/Home.vue'
export default {
components: {
  Home,
},
head() {
        return {
            title: "Crossing the Finish Line",
            meta: [
                {
                    hid: "description",
                    name: "description",
                    content: "Hope to inspire some people to stay active."
                }
            ]
        }
    }
}
</script>
