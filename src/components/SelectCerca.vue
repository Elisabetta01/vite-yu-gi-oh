<script >

     import {store} from '../store'

     export default{
          name: "SelectCerca",
          data(){
               return{
                    store
               }
          }
     }

</script>

<template>
     <div>
          <select class="form-select" aria-label="Default select example" placeholder="Search"
          v-model="store.testoCerca"
          @click.prevent="$emit('cercaEmit')">
               <option value="Alien">Alien</option>
               <option value="Noble Knight">Noble Knight</option>
               <option value="@Ignister">@Ignister</option>
               <option value="Unchained">Unchained</option>
               <option value="Abyss Actor">Abyss Actor</option>
               <option value="Mermail">Mermail</option>
               <option value="Adamancipator">Adamancipator</option>
               <option value="ABC">ABC</option>
          </select>
     </div>
</template>


<style lang="scss" scoped>

</style>