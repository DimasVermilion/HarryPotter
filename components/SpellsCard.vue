<template>
    <div class="card text-center">
        <p class="font-bold text-black m-4">Spell Name: {{ spells.spell }}</p>
        <p class="font-bold text-black m-4">Efek : {{ spells.use }}</p>

        
    </div>
</template>

<script setup>
const { spells } = defineProps(['spells'])

</script>

<style scoped>
.foto {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }

</style>