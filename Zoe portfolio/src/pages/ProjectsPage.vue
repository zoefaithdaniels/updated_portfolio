<script setup>
const projects = [
  {
    title: 'JavaScript Calculator',
    type: 'Web application',
    description: 'A functional calculator built with JavaScript for fast and accurate everyday calculations.',
    link: 'https://zoe-calculator.netlify.app/',
    image: '/project-calculator.webp',
    imageFit: 'contain',
  },
  {
    title: 'Book Store',
    type: 'Web application',
    description: 'An online bookstore experience for browsing and discovering books.',
    link: 'https://dev-swift-books.pantheonsite.io/home/',
    image: '/project-book-store.jpg',
  },
  {
    title: 'Gaming Store',
    type: 'Web application',
    description: 'An online gaming store experience for exploring games and gaming products.',
    link: 'https://dev-bazu.pantheonsite.io/',
    image: '/project-gaming-store.jpg',
  },
]
</script>

<template>
  <section id="projects" class="page-section projects-page">
    <div class="projects-decoration" aria-hidden="true"></div>
    <div class="projects-dots" aria-hidden="true"></div>

    <div class="section-inner projects-inner">
      <header class="projects-header">
        <p class="eyebrow projects-eyebrow">Projects</p>
      </header>

      <div class="project-grid">
        <article v-for="(project, index) in projects" :key="project.title" class="project-card">
          <div class="project-image">
            <img
              :src="project.image"
              :alt="`${project.title} preview`"
              :class="{ 'project-image-contain': project.imageFit === 'contain' }"
            />
          </div>
          <div class="project-card-top">
            <span class="project-number">0{{ index + 1 }}</span>
            <span class="project-type">{{ project.type }}</span>
          </div>
          <div class="project-card-copy">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
          </div>
          <a
            v-if="project.link"
            class="project-arrow"
            :href="project.link"
            target="_blank"
            rel="noreferrer"
            :aria-label="`Open ${project.title}`"
          >↗</a>
          <span v-else class="project-arrow" aria-hidden="true">↗</span>
        </article>
      </div>
    </div>
  </section>
</template>
