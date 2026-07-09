<script setup>
const experience = [
  {
    role: 'Portfolio development',
    period: 'Current',
    detail: 'Creating a Vue portfolio foundation with clear sections and room to grow.',
  },
  {
    role: 'Learning and practice',
    period: 'Ongoing',
    detail: 'Building practical web skills through projects, iteration, and feedback.',
  },
]
</script>

<template>
  <section id="experience" class="page-section">
    <div class="section-inner">
      <p class="eyebrow">Experience</p>
      <div class="section-heading">
        <h2>Experience timeline</h2>
        <p>Add education, work experience, internships, freelance work, or milestones.</p>
      </div>
      <div class="timeline">
        <article v-for="item in experience" :key="item.role" class="timeline-item">
          <span>{{ item.period }}</span>
          <div>
            <h3>{{ item.role }}</h3>
            <p>{{ item.detail }}</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
