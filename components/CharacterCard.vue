<template>
    <div class="card text-center">
        <p class="font-bold text-black m-4">Full Name : {{ chars.fullName}}</p>
        <p class="font-bold text-black m-4">NickName : {{ chars.nickname}}</p>
        <img :src="chars.image" alt="foto Books" class="foto">
        <p class="text-sm text-black">House: {{ chars.hogwartsHouse }}</p>
        <p class="text-sm text-black">Actor: {{ chars.interpretedBy }}</p>

    <div v-if="chars.children && chars.children.length > 0" class="mt-2">
        <p class="font-semibold text-black">Children:</p>
        <ul class="list-disc list-inside text-left text-sm text-gray-700">
        <li v-for="(child, index) in chars.children" :key="index">{{ child }}</li>
      </ul>
    </div>

        
    </div>
</template>

<script setup>
const { chars } = defineProps(['chars'])

</script>

<style scoped>
.foto {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }

</style>