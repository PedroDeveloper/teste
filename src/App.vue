<template>
<v-app>
  <navegation></navegation>
  <foote> </foote>
</v-app>
</template>

<script>
// import navegation from "./components/Navigation"
import navegation from "./components/Navigation"
import foote from "./components/Footer"
export default {
  
  name: 'App',

    components:{
      navegation,
      foote,
    },
  data: () => ({
   
  }),
};
</script>

