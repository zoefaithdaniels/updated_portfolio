<script setup>
const projects = [
  {
    title: 'Personal portfolio',
    type: 'Vue app',
    description: 'A responsive portfolio website with space for work, skills, and contact details.',
  },
  {
    title: 'Project placeholder',
    type: 'Case study',
    description: 'Replace this with a real project, what you built, and what problem it solved.',
  },
  {
    title: 'Creative work',
    type: 'Showcase',
    description: 'Use this card for visual work, writing, design, development, or collaborations.',
  },
]
</script>

<template>
  <section id="projects" class="page-section muted-section">
    <div class="section-inner">
      <p class="eyebrow">Projects</p>
      <div class="section-heading">
        <h2>Selected work</h2>
        <p>Project cards are ready for your real portfolio pieces.</p>
      </div>
      <div class="project-grid">
        <article v-for="project in projects" :key="project.title" class="project-card">
          <span>{{ project.type }}</span>
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </article>
      </div>
    </div>
  </section>
</template>
