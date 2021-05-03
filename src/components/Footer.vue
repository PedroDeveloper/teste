<template>
<v-app>

    <v-footer color="rgba(90,13,4,255)" absolute >
        <v-col cols="12" v-show="isMobile">
            <v-row justify="center">
                <h2 class="white--text">Fale Conosco</h2>
            </v-row>
        </v-col>

        <!-- LINHA PARA A LOGO 
        <v-row style="border: 1px solid orange">
            <v-img  height="120" src="@/assets/logo2.png" alt="a"></v-img>
        </v-row> -->

        <v-row justify="space-between" justify-md="end" 
            align="center">
            <span  v-if="!isMobile" class="white--text mr-1">@FEIJONES</span>
            <div v-for="(icon,i) in icons" :key="i"
                icon
            >
           
                <v-col  cols="12" md="2" xl="12">
                    
                      <v-row >
                        <v-btn  class="mr-1 my-3" :color=icon.btnColor 
                            fab :small=!isMobile
                            @click="icon.cta"
                        >
                            <v-icon  :color=icon.color>{{icon.icon}}</v-icon>
                        </v-btn>
                    </v-row>
                </v-col>
          </div>
        </v-row>

        <v-col cols="12" class="my-3" v-if="isMobile">
            <v-row justify="center">

              <v-img :height="isMobile ? '140' : '250' " src="@/assets/logoFooter.png"></v-img>

            </v-row>
        </v-col>


        <v-col  class="mt-4" cols="12">
            <v-row justify="center" justify-md="end" justify-lg="end">
                <span class="h2" >Endereço: Av. Urbana, Ponto certo</span>
            </v-row>
        </v-col>
    </v-footer>

</v-app>
<!-- <v-app>
    <v-container>
        
<v-footer
    padless
    absolute
>
    <v-card
    elevation="0"
    color="black"
  
    >
    <v-card-title >
        <v-card-text align="center" class="h3 mb-2" >Fale Conosco</v-card-text>
    </v-card-title>
        <v-row  justify="center">
         <div
                    v-for="(icon,i) in icons"
                    :key="i"
                    icon
                    >
            <v-col  >
                <v-row  justify="center">
                    <v-btn class="mr-4" :color=icon.btnColor fab>
                    <v-icon size="55px" :color=icon.color>{{icon.icon}}</v-icon>
                    </v-btn>
                </v-row>
            </v-col>
          </div>

        </v-row>
       <v-row class="mt-12" justify="center"> 
           <v-col cols="12">
               <v-row class="mb-11" justify="center">
                <img src="@/assets/logoFooter.png">
               </v-row>
           </v-col>
       </v-row>
       
    </v-card>
    </v-footer>   
    <v-footer color="rgba(90,13,4,255)" absolute padless> 
           <v-col cols="12">
               <v-row justify="center">
                 <span class="h2" >Endereço: Av. Urbana, Ponto certo</span>
               </v-row>
           </v-col>
    </v-footer>
   
  </v-container>
</v-app> -->
</template>

<script>


export default {

 
   name:'Footer',
    data:()=>({

        icons:[

                { 
                    icon:"mdi-whatsapp", color:"white", btnColor:"green", cta: () => {
                        var url = `https://api.whatsapp.com/send?phone=${5571999992891}&text=Olá, gostaria de ver o cardapio!`
                        window.open(url, '_blank')
                    }
                },
                {
                    icon:"mdi-instagram", color:"white",btnColor:"red", cta: () => {
                        alert("Em breve...")
                    }
                },
                {
                    icon:"mdi-facebook", color:"white",btnColor:"blue", cta: () => {
                         alert("Em breve...")
                    }
                },
                {
                    icon:"mdi-twitter", color:"white",btnColor:"blue", cta: () => {
                         alert("Em breve...")
                    }
                }
             ]
    }),

    computed: {
        isMobile () {
            switch(this.$vuetify.breakpoint.name) {
                case 'xs':
                    return true
                case 'sm':
                    return true
                default: 
                    return false
            }
        }
    }

    
}
</script>

<style scoped>
.h2{
    color: white;
    font-size:100% ;
}
    .h3{
        color: white;
        font-size: 130%;
    }
</style>