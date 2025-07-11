<template>
    <div>
        <h2 class="font-bold text-black text-center"> characters Harry Potter</h2>
        <div class="grid grid-cols-2 gap-5">
            <div v-for="c in chars">
                <CharacterCard :chars="c"/>

            </div>

        </div>
    </div>
</template>

<script setup>
import CharacterCard from '~/components/CharacterCard.vue'

definePageMeta({
    layout:'default'
})
 
const { data:chars } = await useFetch('https://potterapi-fedeperin.vercel.app/en/characters/')



</script>


<style  scoped>
h2 {
    font-size: large;
    margin-top: auto;
}

</style>