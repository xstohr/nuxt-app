<template>
    <Nav></Nav>
    <h1 class="text-center text-xl uppercase text-gray-600 font-semibold py-5">My List</h1>
    <div v-if="data != null">
        <item />
    </div>
    <div v-else class="text-center text-xl text-slate-100 mt-10">
        <span class="bg-red-500 p-4 rounded-lg">You're list of favourites is empty right now!</span>
    </div>
</template>

<script setup lang="ts">

const { pending, data: posts } = useLazyFetch('/api/favourites')
watch(posts, (newPosts) => {

})

</script>