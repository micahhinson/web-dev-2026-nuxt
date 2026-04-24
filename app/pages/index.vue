<template>
   <div>
      <UPageHero
    title="Ultimate Vue UI library"
    description="A Nuxt/Vue-integrated UI library providing a rich set of fully-styled, accessible and highly customizable components for building modern web applications."
    :links="links"
  />
   </div>
</template>
<script setup>
const links = [
   {
      label: "Portfolio",
      to: "/portfolio"
   },
   {
      label: "Contact",
      to: "/contact"
   },
   
]
</script>