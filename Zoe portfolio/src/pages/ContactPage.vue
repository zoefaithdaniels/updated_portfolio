<script setup>
const contactItems = [
  {
    label: 'LinkedIn',
    value: 'linkedin.com/in/zoe-daniels-4290b4256/',
    href: 'https://linkedin.com/in/zoe-daniels-4290b4256/',
    icon: 'in',
  },
  {
    label: 'Email',
    value: 'zoedaniels094@gmail.com',
    href: 'mailto:zoedaniels094@gmail.com',
    icon: '✉',
  },
  {
    label: 'Phone',
    value: '084-755-3693',
    href: 'tel:+27847553693',
    icon: '☎',
  },
  {
    label: 'Website',
    value: 'dev-zoedaniels.pantheonsite.io/home/',
    href: 'https://dev-zoedaniels.pantheonsite.io/home/',
    icon: '◎',
  },
  {
    label: 'Location',
    value: 'Bishop Lavis, Cape Town, South Africa',
    icon: '⌖',
  },
]

function sendMessage(event) {
  const data = new FormData(event.currentTarget)
  const subject = encodeURIComponent(data.get('subject'))
  const body = encodeURIComponent(
    `Name: ${data.get('name')}\nEmail: ${data.get('email')}\n\n${data.get('message')}`,
  )

  window.location.href = `mailto:zoedaniels094@gmail.com?subject=${subject}&body=${body}`
}
</script>

<template>
  <section id="contact" class="page-section contact-page">
    <div class="contact-shape contact-shape-top" aria-hidden="true"></div>
    <div class="contact-shape contact-shape-bottom" aria-hidden="true"></div>
    <div class="contact-dots" aria-hidden="true"></div>

    <div class="section-inner contact-inner">
      <header class="contact-intro">
        <p class="eyebrow contact-eyebrow">Get in touch</p>
      </header>

      <div class="contact-layout">
        <article class="contact-panel contact-info-panel">
          <div class="contact-panel-heading">
            <span class="contact-heading-icon" aria-hidden="true">☎</span>
            <div>
              <h2>Contact information</h2>
              <p>Here’s how you can reach me. I’ll get back to you as soon as possible.</p>
            </div>
          </div>

          <ul class="contact-list">
            <li v-for="item in contactItems" :key="item.label">
              <span class="contact-item-icon" aria-hidden="true">{{ item.icon }}</span>
              <div>
                <strong>{{ item.label }}</strong>
                <a v-if="item.href" :href="item.href" target="_blank" rel="noreferrer">
                  {{ item.value }}
                </a>
                <p v-else>{{ item.value }}</p>
              </div>
            </li>
          </ul>
        </article>

        <article class="contact-panel contact-form-panel">
          <div class="contact-panel-heading">
            <span class="contact-heading-icon" aria-hidden="true">➤</span>
            <div>
              <h2>Send me a message</h2>
            </div>
          </div>

          <form class="contact-form" @submit.prevent="sendMessage">
            <label>
              Your name
              <input name="name" type="text" placeholder="Enter your name" required />
            </label>
            <label>
              Your email
              <input name="email" type="email" placeholder="Enter your email" required />
            </label>
            <label>
              Subject
              <input name="subject" type="text" placeholder="Enter subject" required />
            </label>
            <label>
              Message
              <textarea name="message" rows="5" placeholder="Write your message here..." required></textarea>
            </label>
            <button class="contact-submit" type="submit">➤ <span>Send message</span></button>
          </form>

        </article>
      </div>
    </div>
  </section>
</template>
