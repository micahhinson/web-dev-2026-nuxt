<script setup>
import { z } from 'zod'

useHead({
  title: 'Contact — Atlas Studio',
  meta: [
    { name: 'description', content: 'Get in touch with Atlas Studio about a project.' }
  ]
})

const toast = useToast()

const schema = z.object({
  name:    z.string().min(2, 'Please enter your name'),
  email:   z.string().email('Please enter a valid email'),
  topic:   z.string().min(1, 'Please pick a topic'),
  message: z.string().min(10, 'Tell us a little more (min. 10 characters)')
})

const state = reactive({
  name: '',
  email: '',
  topic: '',
  message: ''
})

const topics = [
  { label: 'New project',       value: 'project' },
  { label: 'Partnership',       value: 'partnership' },
  { label: 'Speaking / talk',   value: 'speaking' },
  { label: 'Just saying hi',   value: 'hello' }
]

async function onSubmit(event) {
  await new Promise(r => setTimeout(r, 400))
  toast.add({
    title: 'Message sent!',
    description: `Thanks ${event.data.name}, we will be in touch within 2 business days.`,
    icon: 'i-lucide-check',
    color: 'primary'
  })
  Object.assign(state, { name: '', email: '', topic: '', message: '' })
}

const faqs = [
  {
    label: 'How long does a typical project take?',
    icon: 'i-lucide-clock',
    content: 'Marketing sites usually take 4–6 weeks. Product engagements run 8–16 weeks depending on scope.'
  },
  {
    label: 'Do you work with early-stage startups?',
    icon: 'i-lucide-rocket',
    content: 'Yes — we love working with founders who are still shaping the product.'
  },
  {
    label: 'What stack do you use?',
    icon: 'i-lucide-layers',
    content: 'Nuxt with Nuxt UI on the front-end, Tailwind for styling, and Postgres + Drizzle for data.'
  },
  {
    label: 'Can we use our own design system?',
    icon: 'i-lucide-puzzle',
    content: 'Absolutely. We can build on top of an existing Figma library, or extend a Storybook you already have.'
  }
]
</script>

<template>
  <UContainer class="py-12 space-y-16">
    <UPageHeader
      headline="Contact"
      title="Tell me about your project."
      description="The more concrete, the better — links, deadlines, and constraints all help."
    />

    <UCard class="max-w-2xl">
      <UForm :schema="schema" :state="state" class="space-y-5" @submit="onSubmit">
        <UFormField label="Your name" name="name" required>
          <UInput v-model="state.name" placeholder="Avery Lin" class="w-full" />
        </UFormField>

        <UFormField label="Email" name="email" required>
          <UInput v-model="state.email" type="email" placeholder="you@company.com" class="w-full" />
        </UFormField>

        <UFormField label="Topic" name="topic" required>
          <USelect v-model="state.topic" :items="topics" placeholder="Pick one" class="w-full" />
        </UFormField>

        <UFormField label="Message" name="message" required>
          <UTextarea
            v-model="state.message"
            :rows="6"
            placeholder="What are you trying to do, and what does success look like?"
            class="w-full"
          />
        </UFormField>

        <div class="pt-2">
          <UButton type="submit" icon="i-lucide-send" trailing size="lg">
            Send message
          </UButton>
        </div>
      </UForm>
    </UCard>

    <UPageSection title="Frequently asked" description="Quick answers before you write.">
      <UAccordion :items="faqs" type="multiple" />
    </UPageSection>
  </UContainer>
</template>