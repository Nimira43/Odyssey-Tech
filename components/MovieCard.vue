<template>
  <div>

  </div>
</template>

<script setup>
  defineProps([
    'title',
    'id',
    'overview',
    'release_date',
    'popularity',
    'poster_path',
    'item'
  ])

  const imageSiteUrl = 'https://image.tmdb.org/t/p/w500/'

</script>
