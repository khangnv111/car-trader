<template>
  <!-- CAR DETAIL PAGE -->
  <div>
    <CarDetailHero/>

    <CarDetailAttributes/>

    <CarDetailDescription/>

    <CarDetailContact/>
  </div>
  <!-- CAR DETAIL PAGE   -->
</template>

<script setup lang="ts">
import CarDetailDescription from "~/components/Car/Detail/CarDetailDescription.vue";
import CarDetailContact from "~/components/Car/Detail/CarDetailContact.vue";

const route = useRoute()
const { toTitleCase } = useUtil()

useHead({
  title: `${toTitleCase(route.params.name)}`,
})

definePageMeta({
  layout: "custom"
})

</script>