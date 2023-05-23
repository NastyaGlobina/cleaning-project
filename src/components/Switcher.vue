<template>
  <div class="home-office">
    <button @click="onClick(1)" :style="{backgroundColor: index===1?activeBgColor:'transparent', color: index===1?activeColor:'#636C81'}" class="btn">Дом</button>
    <button @click="onClick(2)" :style="{backgroundColor: index===2?activeBgColor:'transparent', color: index===2?activeColor:'#636C81'}" class="btn">Офис</button>
  </div>
</template>

<style lang="scss" scoped>

</style>

<script setup>
 import {ref} from "vue";

 const props = defineProps(
     {activeBgColor: {type:String, default: '#5A30F0'},
             activeColor: {type:String, default: '#FFFFFF'}
     }
 )
 const index = ref(1);
   function onClick(e) {
     index.value = e;
   }
</script>
