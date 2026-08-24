<script setup>
import {
  Code2,
  Database,
  FileSignature,
  Lightbulb,
  MessageSquare,
  Monitor,
  TrendingUp,
} from 'lucide-vue-next'

const devicon = 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons'

const overview = [
  { icon: Code2, title: 'Web applications', text: 'Built & maintained' },
  { icon: Database, title: 'SQL databases', text: 'Designed & managed' },
  { icon: Monitor, title: 'Responsive UIs', text: 'User-focused' },
  { icon: Lightbulb, title: 'Always learning', text: 'Growing my skills' },
]

const technicalSkills = [
  { logo: `${devicon}/php/php-original.svg`, name: 'PHP', text: 'Backend development & server-side logic' },
  { logo: `${devicon}/mysql/mysql-original-wordmark.svg`, name: 'MySQL', text: 'Database design, queries & management' },
  { logo: `${devicon}/javascript/javascript-original.svg`, name: 'JavaScript', text: 'Interactive & dynamic web experiences' },
  { logo: `${devicon}/vuejs/vuejs-original.svg`, name: 'Vue.js', text: 'Modern frontend development' },
  { logo: `${devicon}/html5/html5-original.svg`, name: 'HTML', text: 'Semantic & accessible web structure' },
  { logo: `${devicon}/css3/css3-original.svg`, name: 'CSS', text: 'Modern, responsive & clean UI design' },
  { logo: `${devicon}/bootstrap/bootstrap-original.svg`, name: 'Bootstrap', text: 'Fast, responsive layouts' },
  { logo: `${devicon}/nodejs/nodejs-original-wordmark.svg`, name: 'Node.js', text: 'Backend development tools' },
]

const tools = [
  { name: 'VS Code', logo: `${devicon}/vscode/vscode-original.svg` },
  { name: 'Figma', logo: `${devicon}/figma/figma-original.svg` },
  { name: 'WordPress', logo: `${devicon}/wordpress/wordpress-plain.svg` },
  { name: 'Postman', logo: `${devicon}/postman/postman-original.svg` },
  { name: 'Git / GitHub', logo: `${devicon}/github/github-original.svg` },
  { name: 'Azure', logo: `${devicon}/azure/azure-original.svg` },
  { name: 'Notion', logo: `${devicon}/notion/notion-original.svg` },
  { name: 'Mode', monogram: 'M' },
  { name: 'SEO', icon: TrendingUp },
  { name: 'E-signature', icon: FileSignature },
  { name: 'WATI', icon: MessageSquare },
  { name: 'Zapier', monogram: '✦' },
]

</script>

<template>
  <section id="skills" class="page-section skills-page skills-showcase">
    <div class="skills-decoration" aria-hidden="true"></div>
    <div class="skills-dots" aria-hidden="true"></div>

    <div class="section-inner skills-inner">
      <header class="skills-header skills-showcase-header">
        <p class="eyebrow skills-eyebrow">My skills</p>
      </header>

      <div class="skills-overview">
        <article v-for="item in overview" :key="item.title" class="skills-overview-card">
          <span aria-hidden="true"><component :is="item.icon" :size="23" :stroke-width="2.2" /></span>
          <h2>{{ item.title }}</h2>
          <p>{{ item.text }}</p>
        </article>
      </div>

      <section class="skills-block technical-skills-block">
        <header class="skills-block-heading">
          <span aria-hidden="true"><Code2 :size="24" /></span>
          <div>
            <h2>Technical skills</h2>
            <p>Technologies I use to design, develop, and maintain modern web applications.</p>
          </div>
        </header>

        <div class="technical-skills-grid">
          <article v-for="skill in technicalSkills" :key="skill.name" class="technical-skill-card">
            <span class="technical-skill-icon">
              <img :src="skill.logo" :alt="`${skill.name} logo`" />
            </span>
            <h3>{{ skill.name }}</h3>
            <p>{{ skill.text }}</p>
          </article>
        </div>
      </section>

      <section class="skills-block tools-block">
        <header class="skills-block-heading">
          <span aria-hidden="true"><Monitor :size="23" /></span>
          <div>
            <h2>Tools & platforms</h2>
            <p>Software and platforms I use to build, manage, and deliver solutions.</p>
          </div>
        </header>

        <ul class="tools-list">
          <li v-for="tool in tools" :key="tool.name">
            <img v-if="tool.logo" :src="tool.logo" :alt="`${tool.name} logo`" />
            <component v-else-if="tool.icon" :is="tool.icon" :size="18" aria-hidden="true" />
            <span v-else class="tool-monogram" aria-hidden="true">{{ tool.monogram }}</span>
            {{ tool.name }}
          </li>
        </ul>
      </section>

    </div>
  </section>
</template>
