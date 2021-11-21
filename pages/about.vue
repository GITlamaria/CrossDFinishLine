<template>

    <div class="about-page">
        <div class="title">
            <hr>
            <h2>Welcome to my website</h2>
            <h6>Established:  2021</h6>

        </div>
        <b-container>

        <ul>Purpose
            <li>Learn about web page development</li>
            <li>Inspire others to live an active lifestyle</li>
            <li>Show my passion for running</li>
        </ul>
    </b-container>
 
     <hr>

   

    </div>
</template>
<script>

export default {
   head() {
          return {
            title: "About - Crossing the Finish Line!",
            meta: [
              {
                hid: "description",
                name: "description",
                content: "This is a website about running."
              }
            ]
          }
        }
}
</script>


<style scoped>
    .title {
        text-align: center;
    }
    ul {
        font-size: 1.25rem;
        margin-top: 5rem;
    }
    hr {
        margin-top: 5rem;
        margin-bottom: 2rem;
        background-color: #808080;
    }
.about-page {
    min-height: 100vh;      /* to force footer to bottom of page */
}
</style>