<script>
export default {
  name: 'NavBar',

  props: {
    isDark: Boolean,
  },

  emits: ['toggle-dark'],

  data() {
    return {
      scrolled: false,
      mobileOpen: false,

      navLinks: [
        { href: '#about', label: 'About' },
        { href: '#skills', label: 'Skills' },
        { href: '#projects', label: 'Projects' },
        { href: '#experience', label: 'Experience' },
        { href: '#contact', label: 'Contact' },
      ],
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },

  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },

  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 50
    },
  },
}
</script>

<template>
  <nav :class="[
    'fixed top-0 left-0 right-0 z-50 transition-all duration-300',
    scrolled
      ? 'bg-white/90 dark:bg-stone-950/90 backdrop-blur-md shadow-sm'
      : 'bg-transparent'
  ]">
    <div class="max-w-5xl mx-auto px-6 py-4 flex items-center justify-between">

      <!-- Logo / Name -->
      <a href="#hero" class="font-display text-xl text-gray-900 dark:text-white transition-colors">
        PB<span class="text-orange-500">.</span>
      </a>

      <!-- Desktop Nav Links -->
      <ul class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600 dark:text-gray-400">
        <li v-for="link in navLinks" :key="link.href">
          <a :href="link.href" class="hover:text-orange-500 dark:hover:text-orange-500 transition-colors duration-200">
            {{ link.label }}
          </a>
        </li>
      </ul>

      <div class="flex items-center gap-3">

        <!-- Dark / Light Mode Toggle Button -->
        <button @click="$emit('toggle-dark')" class="w-10 h-10 rounded-full flex items-center justify-center
                 text-gray-600 dark:text-gray-400
                 hover:bg-gray-100 dark:hover:bg-gray-800
                 transition-all duration-200" :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'">

          <span v-if="isDark" class="text-lg"><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
              stroke-width="1.5" stroke="currentColor" style="width: 24px; height: 24px;">
              <circle cx="12" cy="12" r="4" />
              <path stroke-linecap="round" stroke-linejoin="round"
                d="M12 2v2m0 16v2M4.93 4.93l1.41 1.41m11.32 11.32l1.41 1.41M2 12h2m16 0h2M6.34 17.66l-1.41 1.41M19.07 4.93l-1.41 1.41" />
            </svg>
          </span>

          <span v-else class="text-lg"><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
              stroke-width="1.5" stroke="currentColor" style="width: 24px; height: 24px;">
              <path stroke-linecap="round" stroke-linejoin="round"
                d="M21.752 15.002A9.72 9.72 0 0 1 18 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 0 0 3 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 0 0 9.002-5.998Z" />
            </svg>
          </span>
        </button>

        <!-- Mobile Hamburger -->
        <button @click="mobileOpen = !mobileOpen" class="md:hidden w-10 h-10 rounded-full flex flex-col items-center justify-center gap-1.5
                 hover:bg-gray-100 dark:hover:bg-gray-800 transition-all">
          <span :class="['block w-5 h-0.5 bg-gray-700 dark:bg-gray-300 transition-all duration-300',
            mobileOpen ? 'rotate-45 translate-y-2' : '']"></span>
          <span :class="['block w-5 h-0.5 bg-gray-700 dark:bg-gray-300 transition-all duration-300',
            mobileOpen ? 'opacity-0' : '']"></span>
          <span :class="['block w-5 h-0.5 bg-gray-700 dark:bg-gray-300 transition-all duration-300',
            mobileOpen ? '-rotate-45 -translate-y-2' : '']"></span>
        </button>

      </div>
    </div>

    <!-- Mobile Menu Dropdown -->
    <div v-if="mobileOpen"
      class="md:hidden bg-white dark:bg-stone-950 border-t border-gray-100 dark:border-stone-800 px-6 py-4">
      <ul class="flex flex-col gap-4 text-sm font-medium text-gray-600 dark:text-gray-400">
        <li v-for="link in navLinks" :key="link.href">
          <a :href="link.href" @click="handleLinkClick(link.href)" :class="[
            'transition-colors duration-200 block py-1',
            currentHash === link.href
              ? 'text-orange-500 font-semibold'
              : 'text-gray-600 dark:text-gray-400 hover:text-orange-500'
          ]">
            {{ link.label }}
          </a>
        </li>
      </ul>
    </div>

  </nav>
</template>
