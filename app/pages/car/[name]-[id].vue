<template>
  <!-- CAR DETAIL PAGE -->
  <div v-if="car">
    <CarDetailHero :car="car" />
    <CarDetailAttributes :features="car.features" />
    <CarDetailDescription :description="car.description" />
    <CarDetailContact/>
  </div>
  <!-- CAR DETAIL PAGE   -->
</template>

<script setup lang="ts">
import CarDetailDescription from "~/components/Car/Detail/CarDetailDescription.vue";
import CarDetailContact from "~/components/Car/Detail/CarDetailContact.vue";

const route = useRoute()
const { cars } = useCars();
const { toTitleCase } = useUtil()

useHead({
  title: `${toTitleCase(route.params.name)}`,
});

const car = computed(() => {
  return cars.find(car => car.id == parseInt(route.params.id));
})

definePageMeta({
  layout: "custom"
})

</script>