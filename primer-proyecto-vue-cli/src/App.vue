<template>
  <div id = "app">
    <!-- <input type = "text" v-model ="nombre"/>
    <Hello :who = "this.nombre" greeting = "what's up?"/> -->
    <!-- El binding se esccibe con :/v-bind: sino lo pone de cadena-->
    Nombre del equipo: 
    <input type="text" v-model = "teamName"/>
    <Info-equipo v-bind:team = "this.teamName"/>
  </div>
</template>

<script>
// import Hello from './components/Hello.vue'
import InfoEquipo from './components/InfoEquipo.vue'

export default {

  components: {
    InfoEquipo
  },
  data(){
    return{
      teamName: '',
    }
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
