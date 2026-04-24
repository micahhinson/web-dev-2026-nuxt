<template>
   <UHeader title="My website">
      <UNavigatonMenu :items="items"/>
      <template #right>
         <UColorModeButton/>
         <button class="bg-neutral-100 dark:bg-neutral-800 px-3 py-1.5 rounded-xl hover:bg-neutral-200">Sign In</button>
      </template>

   </UHeader>
</template>
<script setup>
   const items = [
      {
         label: 'Item 1',
         to: '/',
         children: [
         {
            label: 'Item 1',
            to: '/'
         },
         {
            label: 'Item 2',
            to: '/'
         },
      ],
      }, 
      
      {
         label: 'Item 2',
         to: '/'
      },
      {
         label: 'Item 3',
         to: '/'
      }

   ]
</script>