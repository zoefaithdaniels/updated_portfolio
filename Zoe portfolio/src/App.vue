<script setup>
import { ref } from 'vue'
import AboutPage from './pages/AboutPage.vue'
import ContactPage from './pages/ContactPage.vue'
import ExperiencePage from './pages/ExperiencePage.vue'
import LandingPage from './pages/LandingPage.vue'
import ProjectsPage from './pages/ProjectsPage.vue'
import SkillsPage from './pages/SkillsPage.vue'

const navItems = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Experience', href: '#experience' },
  { label: 'Skills', href: '#skills' },
  { label: 'Projects', href: '#projects' },
  { label: 'Contact', href: '#contact' },
]

const menuOpen = ref(false)
const currentYear = new Date().getFullYear()

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <header class="site-header">
    <div class="site-header-inner">
      <a class="brand" href="#home" aria-label="Zoë Daniels portfolio home" @click="closeMenu">
        <img src="/zoe-daniels-logo.png" alt="Zoë Daniels" />
      </a>

      <button
        class="menu-toggle"
        type="button"
        :aria-expanded="menuOpen"
        aria-controls="primary-navigation"
        aria-label="Toggle navigation menu"
        @click="menuOpen = !menuOpen"
      >
        <span></span><span></span><span></span>
      </button>

      <nav
        id="primary-navigation"
        class="site-nav"
        :class="{ 'is-open': menuOpen }"
        aria-label="Primary navigation"
      >
        <a v-for="item in navItems" :key="item.href" :href="item.href" @click="closeMenu">
          {{ item.label }}
        </a>
        <a class="header-cta" href="#contact" @click="closeMenu">Let's Connect</a>
      </nav>
    </div>
  </header>

  <main>
    <LandingPage />
    <AboutPage />
    <ExperiencePage />
    <SkillsPage />
    <ProjectsPage />
    <ContactPage />
  </main>

  <footer class="site-footer">
    <div class="site-footer-inner">
      <p>© {{ currentYear }} Zoë Daniels</p>
    </div>
  </footer>
</template>
