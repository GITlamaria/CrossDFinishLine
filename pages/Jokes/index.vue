<template>
    <!-- output jokes -->
    <!-- <div>
        <div>
            <AppHeader />
        </div> -->
        <!-- output jokes -->
        <!-- <OneJoke v-for="joke in jokes" :key="joke.id" 
            :id="joke.id" :joke="joke.joke" 
            />
    </div> -->


    <!-- calling cams -->
    <div class="cam">
        <!-- <SkiCam /> -->
    </div>
    
</template>

<script>

import axios from 'axios';
// import OneJoke from '../../components/OneJoke.vue'
// import AppHeader from '../../components/AppHeader.vue'
// import SkiCam from '../../components/SkiCam.vue'


export default {
    components: {
        // OneJoke,
        // AppHeader,
        // SkiCam,
    },

// data() {
//     return {
//       loading: true,
//       countries: null,
//       errored: false
//     }
//   },
//   mounted () {
//   axios
//     .get('https://restcountries.eu/rest/v2/region/americas')  //send request
//     .then(response => (this.countries = response.data))  //data returned
//     .catch(error => {                                     
//       console.log(error)
//       this.errored = true
//     })
//     .finally(() => this.loading = false)
//   },




    data() {
        return {
            jokes: []
        }
    },

    async created() {
    const config = {
      headers: {
        // Accept: "application/json"
        'x-rapidapi-host': 'makevoid-skicams.p.rapidapi.com',
        'x-rapidapi-key': '7fccaca72dmshf6b145ebf11dc24p1bd9fcjsnd28e1969585e'
      }
    };
    try {
      const res = await axios.get("https://makevoid-skicams.p.rapidapi.com/cams.json", config);
      this.jokes = res.data.results;
    // console.log (res.data)
    } catch (err) {
      console.log(err);
    }
  },
    head() {
        return {
            title: "About the App",
            meta: [
                {
                    hid: "description",
                    name: "description",
                    content: "what is the content?"
                }
            ]
        }
    }
}
</script>
