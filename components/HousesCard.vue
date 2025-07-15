<template>
    <div class="card text-center">
        <p class="font-bold text-black m-4">House Name: {{ house.house }}</p>
        <p class="font-bold text-black m-4">Icon : {{ house.emoji }}</p>

    <div v-if="house.colors && house.colors.length > 0" class="mt-2">
        <p class="font-semibold text-black">Color of House</p>
        <ul class="list-disc list-inside text-left text-sm text-gray-700">
        <li v-for="(colors, index) in house.colors" :key="index">{{ colors }}</li>
      </ul>
    </div>

        
    </div>
</template>

<script setup>
const { house } = defineProps(['house'])

</script>

<style scoped>
.foto {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }

</style>