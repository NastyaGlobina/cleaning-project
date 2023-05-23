<template>
  <app-header/>
  <hero/>
  <follower/>
  <cards/>
  <clean/>

</template>

<script>
import AppHeader from "@/layouts/AppHeader.vue";
import Follower from "@/components/Follower.vue";
import Hero from "@/components/Hero.vue";
import Cards from "@/components/Cards.vue";
import Clean from "@/components/Clean.vue";

export default {
  components: {
    AppHeader,
    Follower,
    Hero,
    Cards,
    Clean,
  },
}

</script>

