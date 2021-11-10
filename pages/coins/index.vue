<template>
    <div class="bitcoins">
        <!-- {{info}} -->
        <Coin v-for="coin in coins" :key="coin.id" :coin="coin" />
    </div>
</template>

<script>

import axios from 'axios'
import Coin from '~/components/coin.vue'

export default {

components: {
    Coin
},

data() {
    return {
        // coins: []
        coins: null
    }
},

mounted() {
    axios
        .get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then(response => (this.info = response.data.bpi))
        .catch(error => {
            console.log(error)
        })
}
}


</script>



