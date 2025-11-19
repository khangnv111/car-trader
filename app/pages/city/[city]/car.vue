<template>
  <div>
    <!-- CARS PAGE -->
    <div>
      <div class="mt-32 flex">
        <SideBar/>
        <NuxtPage />
      </div>
    </div>
    <!-- CARS PAGE -->

  </div>
</template>

<script setup lang="ts">
import SideBar from "~/components/Car/SideBar.vue";

const route = useRoute()
const { toTitleCase } = useUtil();
useHead({
  title: `${route.params.make ? toTitleCase(route.params.make) : 'Cars'} in ${toTitleCase(route.params.city)}`,
})

definePageMeta({
  layout: "custom"
})

</script>