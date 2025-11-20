<template>
  <div class="w-full">
    <!-- CAR CARD -->
    <Card v-for="car in cars" :key="car.id" :car="car"/>
    <!-- CAR CARD -->
  </div>
</template>
<script setup lang="ts">
import Card from "~/components/Car/Card.vue";

const {cars} = useCars();

</script>