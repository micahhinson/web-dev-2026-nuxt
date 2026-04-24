<template>
   <main>
      <section class="mx-auto max-w-6xl grid grid-cols-2 gap-4">
         <article v-for="(product, id) in productsApi.products" :key="id" class="p-4 border border-gray-200 rounded-lg">
            <div class="flex flex-row justify-between">
               
                  <div class="flex flex-row gap-2">
                     <UBadge label="Badge"
                     v-for="label in product.tags" color="neutral"  :label="label" />
                  </div>
            </div>
            <div class="font-bold text-lg">
               ${{ product.price }} 
               <span class="font-normal text-sm text-red-500">{{ product.discountPercentage }}% Off
            <div class="text-xl font-bold pt-6">
               {{ product.title }}
            </div>
            <div class="text-sm text-gray-400 mb-2">By {{ product.brand }}</div>
            <div>
               {{product.description}}
            </div>

               </span>
            </div>

      {{ product }}
         </article>
      </section>
   </main>

</template>
<script setup>
const productsApi = await $fetch('https://mockapi.me/products')
</script>