<script >
     
     import SingolaCarta from './SingolaCarta.vue';
     import {store} from '../store'

     export default{
          name: "MainComp",
          components: {
               SingolaCarta
          },
          data(){
               return{
                    store
               }
          }
     }

</script>

<template>
     <div id="main" class="p-4">
          <div class="bg-white p-4 m-4 d-flex flex-wrap justify-content-between">
               <SingolaCarta v-for="(element, index) in store.arrayCarte" :key="index" :infoCarta="element"/>
          </div>
     </div>
</template>


<style lang="scss" scoped>
     #main{
          background-color: #e28743;
     }
</style>