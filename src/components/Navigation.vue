<template> 
<v-app>
 <div>
  <div class="hidden-sm-and-up" >
     <v-navigation-drawer
     v-model="drawer"
     absolute
     app
     temporary
     >
     <v-list>
         <v-list-item>
            <v-list-item-content class=" mt-2 ml-13">
                <v-list-item-title class="title">FEIJONES
                    <v-btn style="z-index:100;" class="ml-8" text color="rgba(90,13,4,255)" small fab @click="drawer = false"> <v-icon> mdi-arrow-left</v-icon> </v-btn>
                 </v-list-item-title> 
                <v-list-item-subtitle class="subTitle">Feijao e Feijoada</v-list-item-subtitle>
            </v-list-item-content>

         </v-list-item>
     </v-list>

  

         <!-- colocar link do componente em 'link' -->
        <v-list dense
         v-for="([color,icon,text],i) in items"
         :key="i"
        >
          <v-divider class="mb-5"></v-divider>
        <v-list-item
            link
        >
          <v-list-item-icon class="justify-start">
                <v-icon  size="30" :color=color> {{icon}} </v-icon> 
          </v-list-item-icon> 

          <v-list-item-content>
             <v-list-item-title>{{text}}</v-list-item-title>
          </v-list-item-content>

         </v-list-item>
        </v-list>
          <v-divider/>
        <img class="mt-16 ml-7" src="@/assets/drawerLogo.png" alt="a">
     </v-navigation-drawer>
  </div>

 <!-- <v-app-bar
     app
     dark
     :height=barSize
     flat
    absolute
    color="black"
    class="appBar2"
     > -->
<!-- <v-col>
    <v-row justify="center">
    <img :class=imgStyle :src=imgSize style="z-index:10;">
    </v-row>
 

  <v-row justify="space-between">
   <v-btn style="z-index:100;" class="btnMenu hidden-sm-and-up" color="rgba(90,13,4,255)" fab>
     <v-app-bar-nav-icon
     @click.stop="drawer = !drawer"
     >
     </v-app-bar-nav-icon>
     </v-btn>
       <v-btn style="z-index:200;" class="btnCart hidden-sm-and-up" color="rgba(90,13,4,255)" fab >
      <v-icon>mdi-cart</v-icon>
     </v-btn>
   </v-row>

   <v-spacer/> -->

    <!-- <v-app-bar
    class="appBar2 expand" 
    color="rgb(90,13,4,255) "
    :width= imgWi
    :height= imgHe
    flat
    >
    <v-row  justify="end" class="mt-9 hidden-md-and-down">
         <v-btn style="position:relative;z-index:100;"  x-large text class="mr-16" >
          <span  class="appBar4  ">Home</span>
        </v-btn>
        <v-btn  x-large text class="mr-16">
          <span class="appBar4">Feijões</span>
        </v-btn>
        <v-btn  x-large class="mr-16" rounded outlined text >
          <span class="appBar4">Fale Conosco</span>
        </v-btn>
    </v-row>
    </v-app-bar>

 
 </v-col>
 </v-app-bar> -->

 <v-app-bar
    
    inverted-scroll
    app
    class="expand hidden-md-and-down " 
    color="rgb(90,13,4,255) "
    :width= imgWi
    :height= imgHe
    flat
    >
    <v-row  justify="end" class="mt-9 hidden-md-and-down">
         <v-btn style="position:relative;z-index:100;"  x-large text class="mr-16" >
          <span  class="appBar4  ">Home</span>
        </v-btn>
        <v-btn  x-large text class="mr-16">
          <span  class="appBar4">Feijões</span>
        </v-btn>
        <v-btn  x-large class="mr-16" rounded outlined text >
          <span class="appBar4">Fale Conosco</span>
        </v-btn>
    </v-row>
    </v-app-bar>
 </div>
</v-app>
</template>

<script>

export default {

    computed:{

        imgSize(){
            switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].src
            default: return this.img[1].src
            }
            
        } ,

        imgWi(){
             switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].width
            default: return this.img[1].width
            }

        },
        imgHe(){
             switch(this.$vuetify.breakpoint.name){

                case"xs":
                    return this.img[0].hight
            default: return this.img[1].hight
            }


        },

        barSize(){
            switch (this.$vuetify.breakpoint.name){
                case"xs":
                    return 200
                default: return 400
            }
        },
        imgStyle(){
            switch (this.$vuetify.breakpoint.name){
                case"xs":
                    return "appBar2"
                default: return ""
            }
            
        }
        

    },
    
    data:() =>({
        drawer:false,
        img:   [
            { 
              src: require ('@/assets/bkMobile.png'),
              width:"",
              hight:"88"
              
            },
            { src: require ('@/assets/bkDesktop.png'),
              width:"22200",
              hight:"165"
            }
            
            ],
        items:[
            ["orange","mdi-home-outline","Home"],
            ["orange","mdi-silverware-variant","Feijões"],
            ["orange","mdi-message","Fale conosco"],
            ["orange","mdi-cart","Carrinho"]



            
        ]
    }),
  
}
</script>

<style scoped>
.title{
    color:#211004 !important;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}
.subTitle{
    color: #8a542e !important;
    font-family: bold;
}
.appBar3{
   padding-top:4rem ;
   font-size: 20px;

}
.appBar4{
    font-size:22px;
    color: white;
}
.spaceBar{
    width:850px ;
}


.elipse{
   
   background-color: red;

}
.btnMenu{
   
    margin-bottom:7.4rem;
}
.btnCart{
  
    margin-bottom:7.4rem ;
}
.backDesktop{
    align-content: center;
}


.appBar2{
    position: absolute;
    bottom: 0px;
   
    
}




</style>