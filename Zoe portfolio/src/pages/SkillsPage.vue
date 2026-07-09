<script setup>
const skills = [
  'Vue',
  'JavaScript',
  'HTML',
  'CSS',
  'Responsive design',
  'UI design',
  'Problem solving',
  'Communication',
]
</script>

<template>
  <section id="skills" class="page-section muted-section">
    <div class="section-inner">
      <p class="eyebrow">Skills</p>
      <div class="section-heading">
        <h2>Tools and strengths</h2>
        <p>
          A flexible set of technical and creative skills that can grow as your
          portfolio develops.
        </p>
      </div>
      <ul class="skill-list">
        <li v-for="skill in skills" :key="skill">{{ skill }}</li>
      </ul>
    </div>
  </section>
</template>
