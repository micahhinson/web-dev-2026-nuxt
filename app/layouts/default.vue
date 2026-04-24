<template>
   <UContainer>
      <!-- Header (nav)-->
      <UHeader title="Micah Hinson">
         <UNavigationMenu :items="items" variant="link" />
      </UHeader>
      <slot/>
      <!-- Footer -->
       <UFooter>
         <template #left> 
            <p class="text-muted text-sm">
          Copyright © {{ new Date().getFullYear() }}
            </p>
         </template>

         <!--Center Nav-->
         <UNavigationMenu :items="items" variant="link" />

         <template #right> 
            <UButton 
               icon="i-simple-icons-linkedin"
               variant="outline"
               color="neutral"
               size="sm"
               to="https://www.linkedin.com/in/micahhinson/"
               target="_blank"
            />
         </template>
       </UFooter>
   </UContainer>
</template>
<script setup>
const items = [
   {
      label: "Home",
      to: "/"
   },
   {
      label: "About",
      to: "/about"
   },
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