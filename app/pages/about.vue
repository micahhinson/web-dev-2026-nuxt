<template>
   <div>
      <Header pageTitle="About Page" />
      <UAccordion :items="items" />
   </div>
</template>
<script>
const items = [
  {
    label: 'Is Nuxt UI free to use?',
    content: 'Yes! Nuxt UI is completely free and open source under the MIT license. All 125+ components are available to everyone.'
  },
  {
    label: 'Can I use Nuxt UI with Vue without Nuxt?',
    content: 'Yes! While optimized for Nuxt, Nuxt UI works perfectly with standalone Vue projects via our Vite plugin. You can follow the [installation guide](/docs/getting-started/installation/vue) to get started.'
  },
  {
    label: 'Is Nuxt UI production-ready?',
    content: 'Yes! Nuxt UI is used in production by thousands of applications with extensive tests, regular updates, and active maintenance.'
  }
]
</script>