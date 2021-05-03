<template>
 
    <section id="hero">
      <v-parallax
    dark
    src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    height="750"
  >
    <v-row
      align="center"
      justify="center"
    >
      <v-col
        class="text-center"
        cols="12"
      >
        <h1 class='rotate-text font-weight-bold'>
          O Brasileiro
        </h1>
        <h2>
          <v-icon>mdi-heart-outline</v-icon> feijão!
        </h2>
      </v-col>
    </v-row>
  </v-parallax>
    </section>
  
</template>

<script>
  export default {
    name: 'Home',

    data: () => ({
      
    }),
  }
</script>

<style scoped>
  .rotate-text {
     -ms-transform: skewY(20deg); /* IE 9 */
    transform: rotate(5deg) !important;
  }
</style>
