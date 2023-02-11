<template>
  <Estudiante/>
</template>

<script>
import Estudiante from "@/components/Estudiante.vue";
export default {
  name: 'App',
  components: {
    Estudiante
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
}
</style>
