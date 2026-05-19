<script>
import profileImg from '../assets/profile.jpg'

export default {
  name: 'HeroSection',

  data() {
    return {
      roles: [
        'UX Designer',
        'IT Student',
        'SIT KMUTT',
      ],

      currentRoleIndex: 0,
      displayedRole: '',
      isDeleting: false, 
      profileImage: profileImg,
    }
  },

  mounted() {
    this.initReveal()

    this.typeWriter()
  },

  methods: {
    typeWriter() {
      const currentRole = this.roles[this.currentRoleIndex]

      if (!this.isDeleting) {

        this.displayedRole = currentRole.slice(0, this.displayedRole.length + 1)

        if (this.displayedRole === currentRole) {

          setTimeout(() => {
            this.isDeleting = true
            this.typeWriter()
          }, 2000)
          return
        }
      } else {

        this.displayedRole = currentRole.slice(0, this.displayedRole.length - 1)

        if (this.displayedRole === '') {

          this.isDeleting = false
          this.currentRoleIndex = (this.currentRoleIndex + 1) % this.roles.length
        }
      }

      const speed = this.isDeleting ? 60 : 100
      setTimeout(() => this.typeWriter(), speed)
    },

    initReveal() {
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add('visible')
            }
          })
        },
        { threshold: 0.1 } 
      )

      document.querySelectorAll('.reveal').forEach((el) => {
        observer.observe(el)
      })
    },
  },
}
</script>

<template>
  <section id="hero" class="min-h-0 lg:min-h-screen flex items-center pt-24 pb-12 lg:py-20">
    <div class="section-wrapper w-full">

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12 items-center">

        <div class="flex flex-col items-center lg:items-start text-center lg:text-left">

          <div class="reveal mb-4 md:mb-6">
            <span class="badge">Hello, I'm</span>
          </div>

          <div class="reveal reveal-delay-1 block lg:hidden mb-6 mx-auto">
            <div class="relative">
              <div class="absolute -inset-2 rounded-2xl border-2 border-orange-500/20 -rotate-3"></div>
              <div
                class="relative w-48 h-48 md:w-56 md:h-56 rounded-2xl overflow-hidden bg-gradient-to-br from-orange-500/20 to-orange-500/5 flex items-center justify-center">
                <img v-if="profileImage" :src="profileImage" alt="Profile photo" class="w-full h-full object-cover" />
              </div>
            </div>
          </div>

          <h1
            class="reveal reveal-delay-1 font-display text-4xl sm:text-5xl md:text-5xl lg:text-7xl text-gray-900 dark:text-white leading-tight mb-4 max-w-xl">
            Papan Boonyakijmaitree
          </h1>

          <div
            class="reveal reveal-delay-2 flex items-center gap-2 text-lg md:text-2xl text-orange-500 font-medium mb-4 md:mb-6">
            <span>{{ displayedRole }}</span>
            <span class="animate-blink text-orange-500">|</span>
          </div>

          <p
            class="reveal reveal-delay-3 text-gray-500 dark:text-gray-400 text-base md:text-lg leading-relaxed mb-6 md:mb-8 max-w-md">
            An IT student at SIT KMUTT who enjoys practicing and thinking about UX.
          </p>

          <div class="reveal reveal-delay-4 flex flex-wrap justify-center lg:justify-start gap-4">
            <a href="#projects" class="btn-primary">View Projects</a>
            <a href="#contact" class="btn-ghost">Contact Me</a>
          </div>

          <div
            class="reveal reveal-delay-5 mt-10 lg:mt-16 flex items-center gap-3 text-gray-400 dark:text-gray-600 text-sm">
            <div class="w-8 h-px bg-gray-300 dark:bg-stone-700"></div>
            <span>Scroll to explore</span>
          </div>
        </div>

        <div class="reveal reveal-delay-2 hidden lg:flex justify-end">
          <div class="relative">
            <div class="absolute -inset-3 rounded-3xl border-2 border-orange-500/20 -rotate-3"></div>
            <div
              class="relative w-64 h-64 lg:w-72 lg:h-72 rounded-3xl overflow-hidden bg-gradient-to-br from-orange-500/20 to-orange-500/5 flex items-center justify-center">
              <img v-if="profileImage" :src="profileImage" alt="Profile photo" class="w-full h-full object-cover" />
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

