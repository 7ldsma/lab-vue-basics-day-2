<template>
  <div class="">
    <div>
      <navbar/>
    </div>

    <div class="px-8 md:px-12 md:mx-28 h-80">
      {{ sumatoria }}
      <div v-if="hola">
        <mensaje/>
      </div>

    </div>


    <div class="bg-[#c9c19f] h-32 bottom-0">
      <footercomp/>
    </div>
  </div>
</template>

<script>
import navbar from './components/navbar.vue'
import footercomp from './components/footercomp.vue'
import mensaje from './components/mensaje.vue'

export default {
  components: {
    navbar,
    footercomp,
    mensaje
  },

  data(){
    return {
      suma : 2 + 2,
    }
  },

  computed: {
    sumatoria (){
      return this.suma
    }

  }

};
</script>

<style scoped>
</style>