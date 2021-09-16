<template>
  <div id = "container">
      <h1>Informacion de equipo</h1>
      <h3>Id : {{ id }}</h3>
      <button @click="getApi()">Get API</button>
      <!--v-if = "this.team.length >0"-->
      <p>Team: {{ team }}</p>
      <p>TeamShort: {{ teamShort}} </p>
      <p>FormedYear: {{ formedYear}}</p>
      <p>Sport: </p>
      <p>League: </p>

  </div>
</template>

<script>
import axios from 'axios'
export default {
    //props: ['team'],
    props: {
        team: {
            type: String,
            required: true,
            //default: 'Los Angeles Lakers'
            // para este caso no servira de mucho ya que la respuesta responde 
            // a la interaccion con la variable team
        }
    },
    data() {
        return {
            team: string,
            teamShort: string,
            formedYear: string,
        }
    },
    methods: {
    async getApi() {
      return axios
        .get(`https://www.thesportsdb.com/api/v1/json/1/searchteams.php?t=${this.team}`)
        .then(response => {
            //console.log(response);
            this.teamShort = stringify(response.data.teams[0].strTeamShort);
            this.formedYear = stringify(response.data.teams[0].intFormedYear);
      })
    },
  },
  watch: {
      team: async function (newValue, oldValue){
          //console.log('Prop changed: ', newValue, 'was', oldValue)
          await this.getApi();
      }
  }
}
</script>

<style>

</style>