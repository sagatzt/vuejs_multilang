<template>
  <div class="about">
    <h1>{{lang.about}}</h1>
  </div>
</template>

<script>
import { useStore } from 'vuex'
import { computed } from 'vue'

export default {
  setup(){

    return {
      lang: computed(()=>useStore().getters.getLang)
    }
  }
}

</script>
