<template>
    <div>
    <select v-model="lang" class="border p-2 rounded mb-4">
      <option value="en">English</option>
      <option value="es">Español</option>
      <option value="fr">Français</option>
      <option value="it">Italiano</option>
      <option value="pt">Português</option>
      <option value="uk">Українська</option>
    </select>
        <h2 class="font-bold text-black text-center"> Houses Harry Potter</h2>
        <div class="grid grid-cols-2 gap-5">
            <div v-for="h in houses">
                <HousesCard :house="h"/>

            </div>
        </div>
    </div>
</template>

<script setup>
import HousesCard from '~/components/HousesCard.vue';
const lang = ref('en')
const houses = ref([])

async function FetchHouses() {
    const {data, error} = await useFetch(`https://potterapi-fedeperin.vercel.app/${lang.value}/houses/`)
    if (data.value) houses.value = data.value
    if (error.value) console.log('Error Fetch House', error.value)   
}

watch(lang,() => {
    FetchHouses
} )

await FetchHouses()

definePageMeta({
    layout:'default'
})
 



</script>


<style  scoped>
h2 {
    font-size: large;
    margin-top: auto;
}

</style>