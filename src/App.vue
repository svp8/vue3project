<template>
  <Header/>
  <router-view/>
</template>
<script>
import Header from "./components/Header.vue";
export default {
  components:{
    Header,
  },
  setup() {
    
  },
}
</script>
<style lang="scss">
#app {
  font-family: Poppins,Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
h1, p, h2, body, nav ,ul{
  list-style-type: none;
  margin:0;
  padding:0;
} 
button{
  border:0;
  font-family: Poppins, sans-serif;
  background: white;
}
</style>
