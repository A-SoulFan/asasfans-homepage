<template>
  <div class="page-wrapper">
    <Preloader />
    <nuxt />
  </div>
</template>


<script>
  import Preloader from "~/components/Preloader.vue";
  export default {
    components: {
      Preloader
    },
    head(){
      return {
        title: "AsAsFans - 专属于一个魂儿的App"
      }
    }

  }
</script>
