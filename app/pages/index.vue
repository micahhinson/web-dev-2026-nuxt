<script setup>
useHead({
  title: 'Atlas Studio — Home',
  meta: [
    { name: 'description', content: 'Independent design & development studio.' }
  ]
})

const services = [
  {
    title: 'Brand & Identity',
    description: 'Design guides, type ramps, and components.',
    icon: 'i-lucide-palette'
  },
  {
    title: 'Web Design',
    description: 'Partner with teams to build frontend websites.',
    icon: 'i-lucide-layout-dashboard'
  },
  {
    title: 'Development',
    description: 'Production Nuxt and Vue applications with thoughtful architecture.',
    icon: 'i-lucide-code'
  }
]

const ctas = [
  {
    title: 'See my work',
    description: 'Selected case studies.',
    icon: 'i-lucide-images',
    to: '/portfolio',
    linkLabel: 'Browse portfolio'
  },
  {
    title: 'Start a project',
    description: 'Have something in mind? Tell me about it.',
    icon: 'i-lucide-message-circle',
    to: '/contact',
    linkLabel: 'Get in touch'
  }
]
</script>

<template>
  <UContainer class="py-12 space-y-16">
    <UPageHero
      headline="New · Spring 2026"
      title="Motivated to Solve Small Problems that Have BIG IMPACTS."
      description="I am a Junior Product Designer/Manager who is devoted to designing meaningful solutions."
    >
      <template #links>
        <UButton to="/portfolio" size="lg" icon="i-lucide-arrow-right" trailing>
          See my work
        </UButton>
        <UButton to="/about" size="lg" color="neutral" variant="subtle">
          About Me
        </UButton>
      </template>
    </UPageHero>

    <UPageSection title="What I do" description="Partner with startups to help launch new products.">
      <UPageGrid>
        <UPageCard
          v-for="s in services"
          :key="s.title"
          :title="s.title"
          :description="s.description"
          :icon="s.icon"
          variant="subtle"
        />
      </UPageGrid>
    </UPageSection>

    <UPageSection title="Where to next?">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <UPageCTA
          v-for="c in ctas"
          :key="c.title"
          :title="c.title"
          :description="c.description"
          :icon="c.icon"
          variant="subtle"
        >
          <template #links>
            <UButton :to="c.to" icon="i-lucide-arrow-right" trailing>
              {{ c.linkLabel }}
            </UButton>
          </template>
        </UPageCTA>
      </div>
    </UPageSection>
  </UContainer>
</template>