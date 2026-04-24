<template>
   <div>
      <Nav />
      <hr class="my-3">
      <PageTitle :pageTitle="pageTitle" />
   </div>
</template>
<script setup>
const props = defineProps({
   pageTitle: {
      required: true
   }
})
</script>