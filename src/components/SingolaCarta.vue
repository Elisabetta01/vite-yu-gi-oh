<script >
     export default{
          name: "SingolaCarta",
          props: ['infoCarta']
     }
</script>

<template>
     <div>
          <div id="carta" class="card" style="width: 16rem;">
               <img :src="infoCarta.card_images[0].image_url" class="card-img-top" alt="">
               <div class="card-body text-center">
                    <h5 class="card-title">{{ infoCarta.name }}</h5>
                    <p class="card-text">{{ infoCarta.archetype }}</p>
               </div>

          </div>
     </div>
</template>


<style lang="scss" scoped>
     div{
          #carta{
               height: 500px;
               margin-bottom: 20px;
               .card-body{
                    background-color: #e28743;
                    h5{
                         color: white;
                         text-transform: uppercase;
                    }
               }
          }
     }
</style>