<template>
    <b-container fluid class="nba-container">

            <h1 @mouseover="hovered = true" 
            @mouseleave="hovered = false" :class="{'changeColor':hovered}">{{title}}</h1>

        <b-row>
            <b-col class="headings">Team ID</b-col>
            <b-col class="headings">Team Name</b-col>
            <b-col class="headings">Abbreviation</b-col>
            <b-col class="headings">City</b-col>
            <b-col class="headings">Division</b-col>
            <b-col class="headings">Conference</b-col>
        </b-row>

        <!-- add a border when mouse is clicked -->
        <!-- iterate through the teams array and add data to columns based on binded property -->
        <b-row @click="toggleClass()" :class="{'addBorder' :bordered}" 
          v-for="team in teams" :key="team.id" >
            <b-col>{{team.id}}</b-col>
            <b-col>{{team.full_name}}</b-col>
            <b-col>{{team.abbreviation}}</b-col>
            <b-col>{{team.city}}</b-col>
            <b-col>{{team.division}}</b-col>
            <b-col>{{team.conference}}</b-col>
        </b-row>        
    </b-container>
</template>

<script>

import axios from 'axios'


export default {
    
    data() {
        return {
            teams: [],
            title: 'NBA Teams',

            hovered: false,
            bordered: false,
        } 
    },
    methods: {
      toggleClass: function() {
        this.bordered=!this.bordered;
      }
    },
     
    
    async created() {
    const config = {
 
      headers: {
        Accept: "application/json",
        
        'x-rapidapi-host': 'free-nba.p.rapidapi.com',
        'x-rapidapi-key': '7fccaca72dmshf6b145ebf11dc24p1bd9fcjsnd28e1969585e'
      }
    };
    try {
      const res = await axios.get('https://free-nba.p.rapidapi.com/teams', config);   //send request

      this.teams = res.data.data;   //fill teams array with response data

    } catch (err) {
      console.log(err);     //log error if request fails
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
height: 3rem;
}
.headings {
    font-size: 1.5rem;
    height: 3rem;
    text-decoration: underline;
    font-style:italic;
}

h1 {
    text-align: center;
    padding-top: 2.5rem;
    padding-bottom: .5rem;
    color: #1a1970; 
}
.changeColor:hover {
  color: #ff00ff;
  font-size: 3rem;
  font-style: italic;
  text-align: left;
}
.addBorder {
  border: 2px solid #F7E0D2;
  background-color: #7c8daf;

}

</style>



