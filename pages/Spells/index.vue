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

        <h2 class="font-bold text-black text-center"> Spells Harry Potter</h2>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="s in spells">
                <SpellsCard :spells="s"/>

            </div>

        </div>
    </div>
</template>

<script setup>
import SpellsCard from '~/components/SpellsCard.vue';
const lang = ref('en')
const spells = ref([])

async function fetchSpells() {
  const { data, error } = await useFetch(`https://potterapi-fedeperin.vercel.app/${lang.value}/spells/`)
  if (data.value) spells.value = data.value
  if (error.value) console.error("Fetch error:", error.value)
}

watch(lang, () => {
  fetchSpells()
})

await fetchSpells()


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