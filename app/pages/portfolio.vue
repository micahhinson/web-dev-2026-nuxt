<script setup>
useHead({
  title: 'Portfolio — Atlas Studio',
  meta: [
    { name: 'description', content: 'Selected work from Atlas Studio.' }
  ]
})

const projects = [
  {
    id: 1,
    title: 'Real Practice',
    client: 'NU Speech Students',
    year: '2026',
    tag: 'AR/VR Project',
    description: 'A Human-Centered AR/VR Solution for Public Speaking Confidence',
    bg: 'from-brand-500 to-brand-700',
    icon: 'i-lucide-rocket'
  },
  {
    id: 2,
    title: 'Thermo Fisher Scientific Internship',
    client: 'Thermo Fisher Scientific',
    year: '2026',
    tag: 'Onboarding ReDesign',
    description: 'Improving Onboarding Time, Assembly Build Rates, and Quality.',
    bg: 'from-amber-500 to-orange-600',
    icon: 'i-lucide-palette'
  },
  {
    id: 3,
    title: 'Creatio Showcase',
    client: 'NU Creatio',
    year: '2026',
    tag: 'Awards Site',
    description: 'Recognizing High Quality Student Work Online.',
    bg: 'from-sky-500 to-indigo-700',
    icon: 'i-lucide-book-open'
  },
  {
    id: 4,
    title: 'Life Lyrics',
    client: 'Puzzled Songwriters',
    year: '2022',
    tag: 'Mobile App Design Using AI',
    description: 'Using Generative AI to Write Song Lyrics',
    bg: 'from-violet-500 to-fuchsia-700',
    icon: 'i-lucide-layout-dashboard'
  }
]

const photos = [
  { id: 1, src: 'https://www.sparkmicro.com/wp-content/uploads/2023/03/MicrosoftTeams-image-10.jpg', alt: 'Modern office workspace', caption: 'AR/VR Glasses' },
  { id: 2, src: 'https://pidc-construction.com/wp-content/uploads/2023/03/themo-fisher-2.jpg', alt: 'Team collaborating', caption: 'Thermo Fisher Scientific - Assembly Floor' },
  { id: 3, src: 'https://www.zkipster.com/hubfs/Imported_Blog_Media/6800db31467607d7b3158951_award-ceremony-management-2.jpg', alt: 'Design sketches', caption: 'Creatio Showcase' },
  { id: 4, src: 'https://cdn.mos.cms.futurecdn.net/VFLt5vHV7aCoLrLGjP9Qwm-1920-80.jpg', alt: 'Laptop with design mockup', caption: 'Generative AI Mobile App Design' },
  { id: 5, src: 'https://upload.wikimedia.org/wikipedia/commons/3/32/Downtown_Snohomish%2C_WA_-_1st_Street_storefronts.jpg?utm_source=en.wikivoyage.org&utm_campaign=index&utm_content=original', alt: 'Color palette swatches', caption: 'Downtown Snohomish' }
]
</script>

<template>
  <UContainer class="py-12 space-y-16">
    <UPageHeader
      headline="Portfolio"
      title="Work I am proud of."
      description="A selection of case studies created by yours truly."
    />

    <UPageSection title="Featured Case Studies" description="Swipe to explore.">
      <UCarousel
        :items="projects"
        arrows
        dots
        loop
        class="w-full"
      >
        <template #default="{ item }">
          <div
            class="mx-2 flex flex-col justify-end rounded-2xl bg-gradient-to-br p-6 text-white shadow-lg"
            :class="item.bg"
            style="height: 320px"
          >
            <p class="text-sm uppercase tracking-wide opacity-80">
              {{ item.tag }} · {{ item.year }}
            </p>
            <p class="mt-2 font-semibold text-xl">{{ item.title }}</p>
            <p class="mt-1 text-sm opacity-90">{{ item.client }}</p>
            <p class="mt-3 text-sm opacity-80">{{ item.description }}</p>
          </div>
        </template>
      </UCarousel>
    </UPageSection>

    <UPageSection title="Photo gallery" description="A photo carousel using real images.">
      <UCarousel
        :items="photos"
        arrows
        dots
        loop
        class="w-full"
      >
        <template #default="{ item }">
          <figure>
            <img
              :src="item.src"
              :alt="item.alt"
              class="mx-auto rounded-xl object-cover"
              style="height: 360px; width: 100%"
            />
            <figcaption class="mt-3 text-center text-sm text-(--ui-text-muted)">
              {{ item.caption }}
            </figcaption>
          </figure>
        </template>
      </UCarousel>
    </UPageSection>

    <UPageSection title="All projects">
      <UPageGrid>
        <UPageCard
          v-for="p in projects"
          :key="p.id"
          :title="p.title"
          :description="p.description"
          :icon="p.icon"
          variant="subtle"
        >
          <template #footer>
            <UBadge :label="p.tag" color="primary" variant="soft" />
          </template>
        </UPageCard>
      </UPageGrid>
    </UPageSection>
  </UContainer>
</template>