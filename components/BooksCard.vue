<template>
    <div class="card text-center">
        <p class="font-bold text-gray-500 m-4">{{ books.title }}</p>
        <img :src="books.cover" alt="foto Books" class="foto">
        
    </div>
</template>

<script setup>
const { Books } = defineProps(['books'])

</script>

<style scoped>
.foto {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }

</style>