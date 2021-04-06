<template>
  <div class="home">
    <img alt="Vue logo" :src="lang.logo">
    <HelloWorld :msg="lang.hello"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import {computed} from 'vue'
import {useStore} from 'vuex'
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  setup(){

    return {
      lang:computed(()=>useStore().getters.getLang)
    }
  }
}
</script>
