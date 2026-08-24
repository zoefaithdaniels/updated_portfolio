<script setup>
const timelineSections = [
  {
    title: 'Work experience',
    intro: 'The roles and practical experiences that have shaped me as a developer and problem-solver.',
    items: [
      {
        company: 'FutureRent',
        badge: 'FR',
        logo: '/futurerent.png',
        role: 'Intermediate Full Stack Developer',
        period: 'July 2024 – July 2026',
        description:
          'Worked as an Intermediate Full Stack Developer at FutureRent, with responsibilities spanning IT support, frontend development, backend development, database management, and system enhancements.',
        label: 'Key responsibilities',
        highlights: [
          'Developed and maintained web applications using modern technologies.',
          'Created responsive and user-friendly frontend interfaces.',
          'Built and integrated backend APIs and services.',
          'Designed, managed, and optimized databases and wrote complex SQL queries.',
          'Provided IT support and troubleshot technical issues for users.',
          'Collaborated with stakeholders to deliver effective solutions.',
          'Maintained and improved existing systems and workflows.',
          'Ensured code quality, security, and performance best practices.',
          'Worked on the customer experience journey by sending bulk communications, creating marketing campaigns, and building mailers and reusable mailer templates.',
        ],
        technologies: [
          'PHP',
          'MySQL',
          'JavaScript',
          'Vue.js',
          'E-signature',
          'WATI',
          'Zapier',
        ],
      },
      {
        company: 'Boldr',
        badge: 'B',
        logo: '/boldr.png',
        role: 'Support Engineer Intern',
        period: 'August 2023 – March 2024',
        label: 'Key responsibilities',
        highlights: [
          'Triaged and resolved hundreds of customer support tickets by troubleshooting issues and applying my knowledge of SQL.',
          'Consistently adhered to playbooks, delivering quick and accurate resolutions to issues, and demonstrated my proficiency by writing SQL queries to investigate databases and identify root causes with precision.',
          'Worked on the Afresh campaign, resolving store support tickets when users experienced issues with the Afresh app.',
          'Sent customer communications when support tickets were resolved.',
        ],
        technologies: ['MySQL', 'Azure', 'Notion', 'Mode'],
      },
      {
        company: 'Life Choices Academy',
        badge: 'LCA',
        logo: '/life-choices-academy.jpg',
        role: 'Lecturer Assistant',
        period: '2023',
        description:
          'Supported aspiring developers during their learning journey by assisting with coding exercises, troubleshooting technical challenges, and providing mentorship within the classroom environment.',
        label: 'Key contributions',
        highlights: [
          'Mentored new students.',
          'Assisted lecturers in coding classes.',
          'Helped students solve problems.',
        ],
      },
    ],
  },
  {
    title: 'Education',
    items: [
      {
        company: 'Life Choices Studio',
        badge: 'LCS',
        logo: '/life-choices-studio.webp',
        role: 'Learning Journey',
        period: 'March 2023 – August 2023',
        highlights: [
          'Completed a learning journey in the LC Studio, learning Figma, UI/UX design, WordPress, SEO, and PHP.',
        ],
      },
      {
        company: 'Life Choices Academy',
        badge: 'LCA',
        logo: '/life-choices-academy.jpg',
        role: 'Learning Journey',
        period: 'September 2022 – March 2023',
        highlights: [
          'Completed a training bootcamp where I upskilled in multiple programming languages.',
        ],
      },
      {
        company: 'Elsies River High School',
        badge: 'ER',
        logo: '/elsies.png',
        role: 'High School',
        period: '2017 – 2021',
        highlights: ['Completed Grade 12.'],
      },
    ],
  },
  {
    title: 'Volunteer experience',
    items: [
      {
        company: 'BLAC Community',
        badge: 'BC',
        role: 'Volunteer',
        period: 'January 2021 – September 2021',
        highlights: [
          'Volunteered at BLAC, which taught me to take initiative in situations that required me to do so.',
        ],
      },
      {
        company: 'Bergville Primary School',
        badge: 'BPS',
        role: 'Volunteer',
        period: 'January 2022 – June 2022',
        highlights: [
          'Volunteered as a helping hand for the educators.',
          'Learned to be vigilant and patient.',
          'Developed communication skills while working with people daily and learned how to de-escalate conflict.',
        ],
      },
    ],
  },
]
</script>

<template>
  <section id="experience" class="page-section experience-page">
    <div class="experience-decoration" aria-hidden="true"></div>
    <div class="section-inner experience-inner">
      <header class="experience-header">
        <p class="eyebrow experience-eyebrow">My journey</p>
      </header>

      <section
        v-for="section in timelineSections"
        :key="section.title"
        class="experience-group"
      >
        <header class="experience-group-header">
          <h2>{{ section.title }}</h2>
          <p v-if="section.intro">{{ section.intro }}</p>
        </header>

        <div class="experience-timeline">
          <article v-for="item in section.items" :key="`${section.title}-${item.company}-${item.period}`" class="experience-row">
            <aside class="experience-date">
              <span>{{ item.period }}</span>
            </aside>

            <div class="timeline-marker" aria-hidden="true"><span></span></div>

            <div class="experience-card">
              <div class="experience-card-dots" aria-hidden="true"></div>
              <div
                class="company-badge"
                :class="{
                  'company-badge--fill': item.company === 'FutureRent',
                }"
              >
                <img v-if="item.logo" :src="item.logo" :alt="`${item.company} logo`" />
                <span v-else>{{ item.badge }}</span>
              </div>
              <div class="experience-card-content">
                <h3>{{ item.company }}</h3>
                <p class="experience-role">{{ item.role }}</p>
                <p class="experience-period">{{ item.period }}</p>
              </div>

              <p v-if="item.description" class="experience-description">
                {{ item.description }}
              </p>

              <div class="experience-highlights">
                <p v-if="item.label">{{ item.label }}</p>
                <ul>
                  <li v-for="highlight in item.highlights" :key="highlight">
                    {{ highlight }}
                  </li>
                </ul>
              </div>

              <div v-if="item.technologies" class="experience-tech">
                <strong>Technologies:</strong>
                <span v-for="technology in item.technologies" :key="technology">
                  {{ technology }}
                </span>
              </div>
            </div>
          </article>
        </div>
      </section>
    </div>
  </section>
</template>
