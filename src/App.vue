<script >
     
     import NavComp from './components/NavComp.vue';
     import MainComp from './components/MainComp.vue';
     import axios from 'axios';
     import {store} from './store';
     import SelectCerca from './components/SelectCerca.vue';

     export default{
          name: "App",
          components: {
               NavComp,
               MainComp,
               SelectCerca,
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
               chiamataApi() {
                    if (store.testoCerca !== '') {
                         axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.testoCerca}`)
                              .then((res)=>{
                                   console.log(res.data.data)
                                   const datiApi = res.data.data
                                   store.arrayCarte = datiApi
                              })
                    } else {
                         axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=1')
                              .then((res)=>{
                                   const datiApi = res.data.data
                                   store.arrayCarte = datiApi
                              })
                    }
               }
               
          }
     }

</script>

<template>
     <NavComp/>

     <SelectCerca @cercaEmit="chiamataApi"/>

     <MainComp/>

</template>

<style lang="scss">
@use './style/main.scss'

</style>
