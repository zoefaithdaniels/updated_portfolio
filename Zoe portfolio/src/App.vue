<script setup>
import AboutPage from './pages/AboutPage.vue'
import ContactPage from './pages/ContactPage.vue'
import ExperiencePage from './pages/ExperiencePage.vue'
import LandingPage from './pages/LandingPage.vue'
import ProjectsPage from './pages/ProjectsPage.vue'
import SkillsPage from './pages/SkillsPage.vue'

const navItems = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Skills', href: '#skills' },
  { label: 'Projects', href: '#projects' },
  { label: 'Experience', href: '#experience' },
  { label: 'Contact', href: '#contact' },
]
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#home" aria-label="Zoë Daniels portfolio home">
      <img src="/zoe-daniels-logo.png" alt="Zoë Daniels" />
    </a>
    <nav class="site-nav" aria-label="Primary navigation">
      <a v-for="item in navItems" :key="item.href" :href="item.href">
        {{ item.label }}
      </a>
    </nav>
    <a class="header-cta" href="#contact">Let's Connect</a>
  </header>

  <main>
    <LandingPage />
    <AboutPage />
    <SkillsPage />
    <ProjectsPage />
    <ExperiencePage />
    <ContactPage />
  </main>
</template>
