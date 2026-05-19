<template>
  <!-- toggle dark mode -->
  <div :class="{ dark: isDark }">
    <div class="min-h-screen bg-white dark:bg-stone-950 transition-colors duration-300">

      <!-- Navbar -->
      <NavBar :isDark="isDark" @toggle-dark="toggleDark" />

      <!-- Sections -->
      <main>
        <HeroSection />
        <AboutSection />
        <SkillsSection />
        <ProjectsSection />
        <ExperienceSection />
        <ContactSection />
      </main>

      <FooterSection />

    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

export default {
  name: 'App',

  components: {
    NavBar,
    HeroSection,
    AboutSection,
    SkillsSection,
    ProjectsSection,
    ExperienceSection,
    ContactSection,
    FooterSection,
  },

  data() {
    return {
      isDark: localStorage.getItem('theme') === 'dark',
    }
  },

  methods: {
    toggleDark() {
      this.isDark = !this.isDark
      localStorage.setItem('theme', this.isDark ? 'dark' : 'light')
    },
  },
}
</script>
