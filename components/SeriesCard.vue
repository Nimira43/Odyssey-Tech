<template>
    <div>
        <div class="max-w-sm p-6 bg-[#eee] border border-[#ccc] rounded-sm shadow dark:bg-[#111] dark:border-[#333]">
            <NuxtLink @click="changeItemState(item)" :to="`/item/${name}`">
                <img class="rounded-t-sm" :src="`${imageSiteUrl}${poster_path}`" alt="Series">
            </NuxtLink>
            <div class="p-5">
                <span href="#">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-[#111] dark:text-[#eee]">{{ name}}</h5>
                </span>
                <p class="mb-3 font-normal text-[#111] dark:text-[#eee]">First Air Date: {{ first_air_date }}</p>
                <p v-if="overview" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-[#eee] bg-[#ff4500] rounded-sm hover:bg-[#ff7c00] focus:ring-4 focus:outline-none focus:ring-[#eef700] dark:bg-[#ff5500] dark:hover:bg-[#ff4500] dark:focus:ring-[#ff7c00]">
                    {{ overview }}
                </p>
                <p v-else class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-[#eee] bg-[#ff4500] rounded-sm hover:bg-[#ff7c00] focus:ring-4 focus:outline-none focus:ring-[#eef700] dark:bg-[#ff5500] dark:hover:bg-[#ff4500] dark:focus:ring-[#ff7c00]">
                    No Overview Available
                </p>
                
            </div>
        </div>
    </div>
</template>

<script setup>
    defineProps([
        'name',
        'overview',
        'first_air_date',
        'popularity',
        'poster_path',
        'item'
    ])
    const imageSiteUrl = 'https://image.tmdb.org/t/p/w500/'
    const itemState = useState('chosenItem', () => {})
    const changeItemState = (item) => {
        itemState.value = item
    }
    
</script>