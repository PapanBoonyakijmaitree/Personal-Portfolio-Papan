<script>
import imgCookify from '../assets/projects/cookify.png'
import imgMemory from '../assets/projects/memory-test.png'
import imgLearnSpace from '../assets/projects/learnspace.png'
import imgRoomBooking from '../assets/projects/room-booking.png'

export default {
  name: 'ProjectsSection',

  data() {
    return {
      activeCategory: 'All',

      categories: ['All', 'UX/UI Design', 'Frontend'],

      projects: [
        {
          title: 'Cookify',
          description: 'A recipe web application featuring an intuitive search and a clean interface to help users discover new dishes easily.',
          tech: ['Vue.js', 'Tailwind CSS', 'JavaScript', 'Figma'],
          role: 'UI/UX Designer & Frontend Developer',
          category: 'Frontend',
          gradient: 'from-purple-400 to-indigo-500',
          image: imgCookify,
          github: 'https://github.com/PANHAN220/INT250-G07-Cookify.git',
          demo: null,
        },
        {
          title: 'Visual Memory Test',
          description: 'A brain-training web game designed to test and track visual memory limits, developed with a strong focus on interactive layout and user testing.',
          tech: ['User Testing', 'Prototyping', 'Vue.js', 'Figma'],
          role: 'UX Researcher & Frontend Developer',
          category: 'UX/UI Design',
          gradient: 'from-pink-400 to-rose-500',
          image: imgMemory,
          github: 'https://github.com/PANHAN220/INT250-G07-Visual-Memory-Test.git',
          demo: null,
        },
        {
          title: 'LearnSpace',
          description: 'A responsive frontend dashboard exercise crafted to practice component structures, grid layouts, and assignment submission flows.',
          tech: ['Vue.js', 'Tailwind CSS', 'JavaScript'],
          role: 'Frontend Developer',
          category: 'Frontend',
          gradient: 'from-teal-400 to-cyan-500',
          image: imgLearnSpace,
          github: 'https://github.com/PapanBoonyakijmaitree/Exercise-8-LearnSpace.git',
          demo: null,
        },
        {
          title: 'SIT Room Booking',
          description: 'A UI/UX concept design for SIT’s room booking platform, created during the HelloWorld activity to deliver a frictionless experience for students.',
          tech: ['Figma', 'User Research'],
          role: 'UI/UX Designer',
          category: 'UX/UI Design',
          gradient: 'from-amber-400 to-orange-500',
          image: imgRoomBooking,
          github: null,
          demo: 'https://www.figma.com/design/08jkOyjMXHtmHEd6C256Ka/Booking-room-SIT_final?node-id=1-54&t=4GcBcclyca1C6Ps0-1',
        },
      ],
    }
  },

  computed: {
    filteredProjects() {
      if (this.activeCategory === 'All') return this.projects
      return this.projects.filter(p => p.category === this.activeCategory)
    },
  },

  mounted() {
    this.initReveal()
  },

  watch: {
    activeCategory() {

      this.$nextTick(() => {
        this.initReveal()
      })
    }
  },

  methods: {
    initReveal() {
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add('visible')
            }
          })
        },
        { threshold: 0.05 }
      )

      document.querySelectorAll('#projects .reveal').forEach((el) => {
        observer.observe(el)
      })
    },
  }
}
</script>


<template>
  <section id="projects" class="bg-orange-50 dark:bg-stone-900 transition-colors duration-300">
    <div class="section-wrapper">

      <!-- Section Header -->
      <div class="reveal">
        <p class="section-subtitle">03 — Projects</p>
        <h2 class="section-title">My Work</h2>
      </div>

      <div class="reveal reveal-delay-1 flex flex-wrap gap-2 mt-8 mb-10">
        <button v-for="cat in categories" :key="cat" @click="activeCategory = cat" :class="[
          'px-4 py-2 rounded-full text-sm font-medium transition-all duration-200',
          activeCategory === cat
            ? 'bg-orange-500 text-white'
            : 'bg-white dark:bg-stone-800 text-gray-600 dark:text-gray-400 hover:border-orange-500 border border-gray-200 dark:border-stone-700'
        ]">
          {{ cat }}
        </button>
      </div>

      <!-- Project Cards Grid -->
      <div class="grid md:grid-cols-2 gap-6">
        <div v-for="(project, index) in filteredProjects" :key="project.title" class="reveal"
          :class="`reveal-delay-${(index % 2) + 1}`">
          <!-- Card -->
          <div class="group bg-white dark:bg-stone-800 rounded-3xl overflow-hidden
                   border border-gray-100 dark:border-stone-700
                   hover:shadow-xl hover:shadow-orange-500/10 hover:-translate-y-1
                   transition-all duration-300">
            <!-- Project Image / Thumbnail -->
            <div class="relative h-48 bg-gradient-to-br overflow-hidden" :class="project.gradient">

              <img v-if="project.image" :src="project.image" :alt="project.title"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />

              <div class="absolute top-3 left-3">
                <span
                  class="bg-white dark:bg-stone-900/90 text-xs font-medium px-3 py-1 rounded-full text-gray-700 dark:text-gray-300">
                  {{ project.category }}
                </span>
              </div>
            </div>

            <!-- Card Body -->
            <div class="p-6">
              <h3 class="font-display text-xl text-gray-900 dark:text-white mb-2">
                {{ project.title }}
              </h3>

              <p class="text-sm text-gray-500 dark:text-gray-400 leading-relaxed mb-4">
                {{ project.description }}
              </p>

              <!-- Tech Stack Tags -->
              <div class="flex flex-wrap gap-1.5 mb-5">
                <span v-for="tech in project.tech" :key="tech"
                  class="text-xs bg-orange-500/10 text-orange-500 px-2.5 py-1 rounded-full">
                  {{ tech }}
                </span>
              </div>

              <!-- Role + Links -->
              <div class="flex items-center justify-between">
                <p class="text-xs text-gray-400 dark:text-gray-500">
                  Role: <span class="font-medium text-gray-600 dark:text-gray-300">{{ project.role }}</span>
                </p>
                <div class="flex gap-3">
                  <!-- GitHub Link -->
                  <a v-if="project.github" :href="project.github" target="_blank"
                    class="text-xs text-gray-500 hover:text-orange-500 dark:hover:text-orange-500-light transition-colors flex items-center gap-1">
                    GitHub →
                  </a>
                  <!-- Live Demo Link -->
                  <a v-if="project.demo" :href="project.demo" target="_blank"
                    class="text-xs text-gray-500 hover:text-orange-500 transition-colors flex items-center gap-1 font-medium">
                    Live Demo →
                  </a>
                </div>
              </div>
            </div>

          </div>
        </div>
      </div>

    </div>
  </section>
</template>