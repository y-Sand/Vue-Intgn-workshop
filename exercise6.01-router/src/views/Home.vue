<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  methods: {
    navega:function(){
      // this.$router invocar el router para navegar a una ruta, push-> vete a la ruta
      // aqui no es un arreglo y significa otra cosa
      this.$router.push("/messages");
    },
  },
  components: {
    HelloWorld
  }
}
</script>
