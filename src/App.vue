<template>
  <div class="">
    <div>
      <navbar/>
    </div>

    <div class="flex flex-col px-8 md:px-12 md:mx-28 h-80">
      {{ sumatoria }}
      <button class="bg-[#c9c19f] px-6 py-6" @click="mostrarMensaje">Mostrar mensaje</button>
      <button class="bg-[#c9c19f] px-6 py-6" @click="ocultarMensaje">ocultar mensaje</button>
      <div v-if="this.hola">
        Este mensaje se muestra por el valor true de una variable.
      </div>

      <div>
        <button class="bg-gray-300 py-2 px-4 rounded-md" @click="cambiarBg">Cambiar color</button>
        <ul :class="{background: bright}">
          <li v-for="post in posts">{{ post.Title }}</li>
        </ul>

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

export default {
  components: {
    navbar,
    footercomp,
    
  },

  data(){
    return {
      suma : 2 + 2,
      hola: false,
      bright: false,
      posts: [{
          Title: 'Uno',
          Description:'Number1',
          content:'this is a number',
          
          }, 
          {
          Title: 'Dos',
          Description:'Number2',
          content:'this is the second number',
          
          },
          {
          Title: 'Tres',
          Description:'Number3',
          content:'this is not a number',
        
          }

      ]
    }
  },

  computed: {
    sumatoria (){
      return this.suma
    }

  },
  methods: {
    mostrarMensaje (){
      this.hola = true
    },
    ocultarMensaje(){
      this.hola = false
    },
    cambiarBg (){
      this.bright = true
    }

  }

};
</script>

<style scoped>

.background {
  background-color: azure;
}

</style>