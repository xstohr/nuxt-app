<template>
    <div class="mx-5 mb-5">
        <div class="grid md:grid-cols-3 sm:grid-cols-2 grid-cols-1 gap-5 justify-center">
            <div v-for="item of items" :key="item.name" 
                class="relative rounded overflow-hidden shadow-lg">
                <img class="w-full" :src="item.image" :alt="item.title">
                <div class="px-6 py-4">
                    <div class="font-bold text-xl mb-2">{{ item.title }}</div>
                    <div class="my-4 text-sm">height: 
                        <span class="">
                            {{ item.height }}
                        </span>
                    </div>
                    <p class="text-gray-700 text-base pb-16">
                        {{ item.description }}
                    </p>
                    <div class="absolute bottom-6 left-6">
                        <a 
                        class="bg-gray-200 py-2 px-4 rounded text-gray-600 hover:bg-gray-800 hover:text-gray-200 transition duration-300" 
                        @click="favourite">
                        ⭐️
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">

const { data: items, pending, error, refresh } = await useFetch('https://api.nuxtjs.dev/mountains')

const favourite = useState('favourite', () => true)

</script>