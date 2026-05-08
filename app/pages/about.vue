<template>
  <UContainer class="py-12 space-y-16">
    <UPageHeader
      headline="About"
      title="A passionate problem solver, trying to make the world a better place one project at a time."
      description="I am based out of Seattle, Washington."
    />

    <UPageBody>
      <UPageSection title="What I believe" description="The principles that show up in every project.">
        <UPageGrid>
          <UPageCard
            v-for="p in principles"
            :key="p.title"
            :title="p.title"
            :description="p.description"
            :icon="p.icon"
            variant="subtle"
          />
        </UPageGrid>
      </UPageSection>

      <UPageSection title="My Mentors" description="Three people, each different roles.">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
          <UCard v-for="m in team" :key="m.name" class="text-center">
            <UAvatar :src="m.avatar" :alt="m.name" size="2xl" class="mx-auto" />
            <h3 class="mt-4 font-semibold text-lg">{{ m.name }}</h3>
            <p class="mt-1 text-sm text-(--ui-text-muted)">{{ m.role }}</p>
            <p class="mt-2 text-sm text-(--ui-text-muted)">{{ m.bio }}</p>
            <div class="mt-4 flex justify-center gap-3">
              <UButton
                v-if="m.social.twitter"
                :to="m.social.twitter"
                icon="i-simple-icons-x"
                variant="ghost"
                size="sm"
                aria-label="Twitter"
              />
              <UButton
                v-if="m.social.github"
                :to="m.social.github"
                icon="i-simple-icons-github"
                variant="ghost"
                size="sm"
                aria-label="GitHub"
              />
              <UButton
                v-if="m.social.linkedin"
                :to="m.social.linkedin"
                icon="i-simple-icons-linkedin"
                variant="ghost"
                size="sm"
                aria-label="LinkedIn"
              />
            </div>
          </UCard>
        </div>
      </UPageSection>
    </UPageBody>
  </UContainer>
</template>
<script setup>
useHead({
  title: 'About — Atlas Studio',
  meta: [
    { name: 'description', content: 'A studio that takes craft, accessibility, and maintainability seriously.' }
  ]
})

const principles = [
  {
    title: 'Consistent Alignment Always',
    description: 'Fewer visual distractions produce more user engagement.',
    icon: 'i-lucide-feather'
  },
  {
    title: 'Users First, Users Always',
    description: 'People ignore design that ignores people.',
    icon: 'i-lucide-gauge'
  },
  {
    title: 'Iterate, iterate, iterate',
    description: 'Just when you think something cannot get any better, go do more user testing.',
    icon: 'i-lucide-accessibility'
  },
  {
    title: 'Design for tomorrow, not just for today',
    description: 'Plan and think ahead, will this solution be scalable down the road?',
    icon: 'i-lucide-package-check'
  }
]

const team = [
  {
    name: 'Avery Lin',
    role: 'Design lead',
    bio: '10 years crafting identities and interfaces for startups and scale-ups.',
    avatar: 'https://i.pravatar.cc/120?img=15',
    social: { twitter: '#', github: '#' }
  },
  {
    name: 'Marco Reyes',
    role: 'Engineering lead',
    bio: 'Full-stack engineer obsessed with performance, accessibility, and clean architecture.',
    avatar: 'https://i.pravatar.cc/120?img=33',
    social: { github: '#', linkedin: '#' }
  },
  {
    name: 'Hana Okafor',
    role: 'Brand & writing',
    bio: 'Brand strategist and copywriter who makes complicated things feel simple.',
    avatar: 'https://i.pravatar.cc/120?img=47',
    social: { twitter: '#', linkedin: '#' }
  }
]
</script>