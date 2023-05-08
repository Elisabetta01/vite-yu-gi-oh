<script >
     
     import NavComp from './components/NavComp.vue';
     import MainComp from './components/MainComp.vue';
     import axios from 'axios';
     import {store} from './store'

     export default{
          name: "App",
          components: {
               NavComp,
               MainComp,
          },
          
          data(){
               return{
                    store
               }
          },
          created(){
               this.chiamataApi();
          },
          methods: {
               chiamataApi(){
                    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=1')
                         .then((res)=>{
                              console.log(res.data.data)
                              this.store.arrayCarte = res.data.data 
                         })
               }
          }
     }

</script>

<template>
     <NavComp/>
     <MainComp/>
</template>

<style lang="scss">
@use './style/main.scss'
</style>
