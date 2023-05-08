<script >
     
     import NavComp from './components/NavComp.vue';

     export default{
          name: "App",
          components: {
               NavComp,
          }
     }

</script>

<template>
     <NavComp/>
</template>

<style lang="scss">
@use './style/main.scss'
</style>
