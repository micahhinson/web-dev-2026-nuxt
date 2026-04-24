<template>
   <div>
      <Header pageTitle="Contact Page" /> 
      <UForm @submit="processForm">
      <UFormField label="First Name">
         <UInput v-model="firstName"></UInput>
      </UFormField>
       <UFormField label="Last Name">
         <UInput v-model="lastName"></UInput>
      </UFormField>
      <UButton type="submit">
         Submit
      </UButton>
      </UForm>
      <div v-if="submitted == true">
         Hi, my first name is {{ firstName }}
      </div>
   </div>
</template>
<script setup>
const firstname = ref('')
const submittedFirstName = ref('')
const lastname = ref('')
const submittedLastName = ref('')
const submitted = ref(false)
function processForm(event){
   submitted.value = true;
   submittedFirstName.value = firstName.value;
   firstName.value = '';
   submittedLastName.value = firstName.value;
   lastName.value = '';
   alert(`Hi ${submittedfirstName.value} ${submittedLastName.value}`)
}
</script>