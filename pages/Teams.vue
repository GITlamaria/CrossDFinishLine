<template>
    <b-container fluid class="nba-container">

            <h1>{{title}}</h1>


        <b-row>
            <b-col class="headings">Team Name</b-col>
            <b-col class="headings">Abbreviation</b-col>
            <b-col class="headings">City</b-col>
            <b-col class="headings">Division</b-col>
        </b-row>
        <b-row v-for="team in teams" :key="team.id" >
            <b-col>{{team.full_name}}</b-col>
            <b-col>{{team.abbreviation}}</b-col>
            <b-col>{{team.city}}</b-col>
            <b-col>{{team.division}}</b-col>
        </b-row>
        
    </b-container>
</template>

<script>

import axios from 'axios'
export default {
    name: 'Team',

    data() {
        return {
            teams: [],
            title: 'NBA Teams'
        }
    },
    async created() {
    const config = {
    // params: {page: '0', per_page: '25'},
      headers: {
        Accept: "application/json",
        
     'x-rapidapi-host': 'free-nba.p.rapidapi.com',
    'x-rapidapi-key': '7fccaca72dmshf6b145ebf11dc24p1bd9fcjsnd28e1969585e'
      }
    };
    try {
      const res = await axios.get('https://free-nba.p.rapidapi.com/teams', config);
    //   this.cams = res.data.results;
    this.teams = res.data.data;
    console.log (res.data.data)
    } catch (err) {
      console.log(err);
    }
  },
}

</script>

<!-- link to global stylesheet -->
<style src="@/assets/styles/appStyle.css" />

<style lang="scss" scoped>

.row {
    text-align: center;
    
}
.col {
text-align: left;
background-color: #7c8daf;
height: 3rem;
}
.headings {
    background-color: #1a1970;
    color: #F7E0D2;
    font-size: 1.5rem;
    height: 5rem;
}

h1 {
    text-align: center;
    padding-top: 2rem;
    padding-bottom: .5rem;
    
}

</style>



