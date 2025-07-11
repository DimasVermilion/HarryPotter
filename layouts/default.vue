<template>    
    <div>
         <header class="shadow-sm bg-white">
             <nav class="container mx-auto p-4 flex justify-beetween">
             <ul class="flex gap-4">
                <li>
                    <nuxt-link to="/">Home</nuxt-link>
                </li>
                <li>
                    <nuxt-link to="/Books">Books</nuxt-link>
                </li>
                <li>
                    <nuxt-link to="/characters">characters</nuxt-link>
                </li>
                 <li>
                    <nuxt-link to="/houses">Houses</nuxt-link>
                </li>
            </ul> 
        </nav>
    </header>
    
    </div>
    <div class="container mx-auto p-4">
        <slot />
    </div>
</template>


<style scoped>
.router-link-exect-active {

    color: aqua;
}


</style>