<script>
import certVue from '../assets/certs/vue-fundamentals.png'
import certTailwind from '../assets/certs/tailwind-css.png'
import certBootstrap from '../assets/certs/bootstrap.png'

export default {
  name: 'ExperienceSection',

  data() {
    return {
      selectedCertImage: null,

      experiences: [
        {
          date: 'March 2, 2026',
          title: 'Tailwind CSS Specialized Learning',
          organization: 'Coursera (Scrimba)',
          description: 'Completed an intensive 2-hour practical course focusing on utility-first styles. Mastered responsive web layouts and multi-device designs with a final test score of 90%.',
          tags: ['Tailwind CSS', 'Responsive Design', 'CSS Framework'],
        },
        {
          date: 'March 2, 2026',
          title: 'Bootstrap Component Training',
          organization: 'Coursera (Scrimba)',
          description: 'Studied the core structures of Bootstrap 4 framework to accelerate frontend layout prototyping. Achieved a perfect 100% score on building responsive modern web applications.',
          tags: ['Bootstrap', 'Web Layouts', 'CSS Components'],
        },
        {
          date: 'February 27, 2026',
          title: 'Fundamentals of Vue.js Core Study',
          organization: 'Coursera (Board Infinity)',
          description: 'Spent approximately 5 hours mastering the core principles of Vue.js, including components architecture, two-way data binding, and conditional rendering. Concluded with a 95% evaluation score.',
          tags: ['Vue.js', 'JavaScript', 'State Management'],
        }
      ],

      certifications: [
        {
          name: 'Learn Tailwind CSS',
          issuer: 'Scrimba via Coursera',
          image: certTailwind,
        },
        {
          name: 'Learn Bootstrap',
          issuer: 'Scrimba via Coursera',
          image: certBootstrap,
        },
        {
          name: 'Fundamentals of VueJS',
          issuer: 'Board Infinity via Coursera',
          image: certVue,
        },
      ],
    }
  },
}
</script>

<template>
  <section id="experience" class="bg-white dark:bg-stone-950 transition-colors duration-300 py-20">
    <div class="section-wrapper">

      <div class="reveal">
        <p class="section-subtitle">04 — Experience</p>
        <h2 class="section-title">My Journey</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-16 mt-12">

        <div>
          <h3 class="reveal font-display text-xl text-gray-900 dark:text-white mb-8">
            Activities & Experience
          </h3>

          <div class="space-y-0">
            <div v-for="(item, index) in experiences" :key="item.title" class="relative pl-8 pb-8">

              <div v-if="index !== experiences.length - 1"
                class="absolute left-0 top-2 bottom-0 w-0.5 bg-gray-100 dark:bg-stone-800">
              </div>

              <div
                class="absolute -left-[7px] top-1.5 w-4 h-4 rounded-full border-2 border-orange-500 bg-white dark:bg-stone-950 z-10">
              </div>

              <div class="reveal" :class="`reveal-delay-${index + 1}`">
                <p class="text-xs text-orange-500 font-medium mb-1">{{ item.date }}</p>

                <h4 class="font-medium text-gray-900 dark:text-white">{{ item.title }}</h4>
                <p class="text-sm text-gray-500 dark:text-gray-400 mb-2">{{ item.organization }}</p>

                <p class="text-sm text-gray-500 dark:text-gray-400 leading-relaxed">
                  {{ item.description }}
                </p>

                <div class="flex flex-wrap gap-1.5 mt-3">
                  <span v-for="tag in item.tags" :key="tag"
                    class="text-xs bg-gray-100 dark:bg-stone-800 text-gray-600 dark:text-gray-400 px-2.5 py-1 rounded-full">
                    {{ tag }}
                  </span>
                </div>
              </div>

            </div>
          </div>
        </div>

        <div class="space-y-6">
          <h3 class="reveal font-display text-xl text-gray-900 dark:text-white mb-2">
            Certifications
          </h3>

          <div class="space-y-4">
            <div v-for="(cert, index) in certifications" :key="cert.name" @click="selectedCertImage = cert.image" class="reveal bg-gray-100 dark:bg-stone-900 border border-gray-100 dark:border-stone-800 rounded-2xl p-4
                     flex gap-4 items-center translate-y-0 transform-gpu transition-transform duration-300 ease-out 
                     hover:-translate-y-1 hover:shadow-lg cursor-zoom-in group" :class="`reveal-delay-${index + 1}`">
              <div
                class="w-24 h-16 rounded-lg overflow-hidden bg-gray-200 dark:bg-stone-800 flex-shrink-0 border border-gray-200/50 dark:border-stone-700">
                <img v-if="cert.image" :src="cert.image" :alt="cert.name"
                  class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
              </div>

              <div class="flex-1">
                <p
                  class="text-sm font-medium text-gray-900 dark:text-white group-hover:text-orange-500 transition-colors duration-300">
                  {{ cert.name }}
                </p>
                <p class="text-xs text-gray-400 dark:text-gray-500 mt-1">
                  {{ cert.issuer }}
                </p>
              </div>
            </div>
          </div>
        </div>

      </div>
    </div>

    <div v-if="selectedCertImage" @click="selectedCertImage = null"
      class="fixed inset-0 z-50 bg-black/80 backdrop-blur-sm flex items-center justify-center p-4 cursor-zoom-out">
      <div @click.stop
        class="relative max-w-4xl max-h-[85vh] rounded-2xl overflow-hidden shadow-2xl bg-stone-900 border border-stone-800">
        <img :src="selectedCertImage" alt="Enlarged Certification" class="w-full h-full object-contain max-h-[80vh]" />
        <button @click="selectedCertImage = null"
          class="absolute top-4 right-4 bg-black/50 text-white rounded-full p-2 hover:bg-black/80 transition-colors cursor-pointer">
          ✕
        </button>
      </div>
    </div>

  </section>
</template>

