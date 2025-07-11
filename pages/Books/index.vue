<template>
    <div>
        <h2 class="font-bold text-black text-center">List Book about Harry Potter</h2>
        <div class="grid grid-cols-4 gap-5">
            <div v-for="b in books">
                <BooksCard :books="b"/>

            </div>

        </div>
    </div>
</template>

<script setup>
import BooksCard from '~/components/BooksCard.vue';

const {id} = useRoute().params
definePageMeta({
    layout:'default'
})
 
const { data:books } = await useFetch('https://potterapi-fedeperin.vercel.app/en/books/')



</script>


<style  scoped>
h2 {
    font-size: large;
    margin-top: auto;
}

</style>