<template>
  <div id="nav">
    <router-link to="/">{{lang["menu-home"]}}</router-link> |
    <router-link to="/about">{{lang["menu-about"]}}</router-link> 
  </div>
  <Lang />
  <router-view/>
</template>

<script>
import Lang from '@/components/Lang'
import { useStore } from 'vuex'
import { computed } from 'vue'

export default {
  components: {
    Lang
  },
  setup(){

    return {
      lang: computed(()=>useStore().getters.getLang)
    }
  }
}

</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
