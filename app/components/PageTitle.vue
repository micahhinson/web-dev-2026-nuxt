<template>
   <h1 class="text-xl">{{ pageTitle }}</h1>
</template>
<script setup>
const props = defineProps({
   pageTitle: {
      required: true
   }
})
</script>