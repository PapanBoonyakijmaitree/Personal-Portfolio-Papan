<script>
export default {
  name: 'SkillsSection',

  data() {
    return {
      animated: false,

      technicalSkills: [
        { name: 'HTML / CSS', level: 85 },
        { name: 'JavaScript', level: 50 },
        { name: 'Vue.js', level: 75 },
        { name: 'Tailwind CSS', level: 65 },
        { name: 'Figma / UI Design', level: 90 },
        { name: 'Git / GitHub', level: 85 },
      ],

      tools: [
        {
          name: 'Figma',
          icon: `<svg class="w-5 h-5" viewBox="0 0 38 57" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M19 0H9.5C4.25 0 0 4.25 0 9.5C0 14.75 4.25 19 9.5 19H19V0Z" fill="#F24E1E"/><path d="M19 19H9.5C4.25 19 0 23.25 0 28.5C0 33.75 4.25 38 9.5 38H19V19Z" fill="#A259FF"/><path d="M19 38H9.5C4.25 38 0 42.25 0 47.5C0 52.75 4.25 57 9.5 57C14.75 57 19 52.75 19 47.5V38Z" fill="#0ACF83"/><path d="M19 38H28.5C33.75 38 38 33.75 38 28.5C38 23.25 33.75 19 28.5 19H19V38Z" fill="#1ABC9C"/><path d="M38 9.5C38 14.75 33.75 19 28.5 19H19V0H28.5C33.75 0 38 4.25 38 9.5Z" fill="#FF7262"/></svg>`
        },
        {
          name: 'VS Code',
          icon: `<svg class="w-5 h-5" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <mask id="mask0" mask-type="alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="100" height="100">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M70.9119 99.3171C72.4869 99.9307 74.2828 99.8914 75.8725 99.1264L96.4608 89.2197C98.6242 88.1787 100 85.9892 100 83.5872V16.4133C100 14.0113 98.6243 11.8218 96.4609 10.7808L75.8725 0.873756C73.7862 -0.130129 71.3446 0.11576 69.5135 1.44695C69.252 1.63711 69.0028 1.84943 68.769 2.08341L29.3551 38.0415L12.1872 25.0096C10.589 23.7965 8.35363 23.8959 6.86933 25.2461L1.36303 30.2549C-0.452552 31.9064 -0.454633 34.7627 1.35853 36.417L16.2471 50.0001L1.35853 63.5832C-0.454633 65.2374 -0.452552 68.0938 1.36303 69.7453L6.86933 74.7541C8.35363 76.1043 10.589 76.2037 12.1872 74.9905L29.3551 61.9587L68.769 97.9167C69.3925 98.5406 70.1246 99.0104 70.9119 99.3171ZM75.0152 27.2989L45.1091 50.0001L75.0152 72.7012V27.2989Z" fill="white"/>
                  </mask>
                  <g mask="url(#mask0)">
                  <path d="M96.4614 10.7962L75.8569 0.875542C73.4719 -0.272773 70.6217 0.211611 68.75 2.08333L1.29858 63.5832C-0.515693 65.2373 -0.513607 68.0937 1.30308 69.7452L6.81272 74.754C8.29793 76.1042 10.5347 76.2036 12.1338 74.9905L93.3609 13.3699C96.086 11.3026 100 13.2462 100 16.6667V16.4275C100 14.0265 98.6246 11.8378 96.4614 10.7962Z" fill="#0065A9"/>
                  <g filter="url(#filter0_d)">
                  <path d="M96.4614 89.2038L75.8569 99.1245C73.4719 100.273 70.6217 99.7884 68.75 97.9167L1.29858 36.4169C-0.515693 34.7627 -0.513607 31.9063 1.30308 30.2548L6.81272 25.246C8.29793 23.8958 10.5347 23.7964 12.1338 25.0095L93.3609 86.6301C96.086 88.6974 100 86.7538 100 83.3334V83.5726C100 85.9735 98.6246 88.1622 96.4614 89.2038Z" fill="#007ACC"/>
                  </g>
                  <g filter="url(#filter1_d)">
                  <path d="M75.8578 99.1263C73.4721 100.274 70.6219 99.7885 68.75 97.9166C71.0564 100.223 75 98.5895 75 95.3278V4.67213C75 1.41039 71.0564 -0.223106 68.75 2.08329C70.6219 0.211402 73.4721 -0.273666 75.8578 0.873633L96.4587 10.7807C98.6234 11.8217 100 14.0112 100 16.4132V83.5871C100 85.9891 98.6234 88.1786 96.4586 89.2196L75.8578 99.1263Z" fill="#1F9CF0"/>
                  </g>
                  <g style="mix-blend-mode:overlay" opacity="0.25">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M70.8511 99.3171C72.4261 99.9306 74.2221 99.8913 75.8117 99.1264L96.4 89.2197C98.5634 88.1787 99.9392 85.9892 99.9392 83.5871V16.4133C99.9392 14.0112 98.5635 11.8217 96.4001 10.7807L75.8117 0.873695C73.7255 -0.13019 71.2838 0.115699 69.4527 1.44688C69.1912 1.63705 68.942 1.84937 68.7082 2.08335L29.2943 38.0414L12.1264 25.0096C10.5283 23.7964 8.29285 23.8959 6.80855 25.246L1.30225 30.2548C-0.513334 31.9064 -0.515415 34.7627 1.29775 36.4169L16.1863 50L1.29775 63.5832C-0.515415 65.2374 -0.513334 68.0937 1.30225 69.7452L6.80855 74.754C8.29285 76.1042 10.5283 76.2036 12.1264 74.9905L29.2943 61.9586L68.7082 97.9167C69.3317 98.5405 70.0638 99.0104 70.8511 99.3171ZM74.9544 27.2989L45.0483 50L74.9544 72.7012V27.2989Z" fill="url(#paint0_linear)"/>
                  </g>
                  </g>
                  <defs>
                  <filter id="filter0_d" x="-8.39411" y="15.8291" width="116.727" height="92.2456" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                  <feFlood flood-opacity="0" result="BackgroundImageFix"/>
                  <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"/>
                  <feOffset/>
                  <feGaussianBlur stdDeviation="4.16667"/>
                  <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"/>
                  <feBlend mode="overlay" in2="BackgroundImageFix" result="effect1_dropShadow"/>
                  <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow" result="shape"/>
                  </filter>
                  <filter id="filter1_d" x="60.4167" y="-8.07558" width="47.9167" height="116.151" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                  <feFlood flood-opacity="0" result="BackgroundImageFix"/>
                  <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"/>
                  <feOffset/>
                  <feGaussianBlur stdDeviation="4.16667"/>
                  <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"/>
                  <feBlend mode="overlay" in2="BackgroundImageFix" result="effect1_dropShadow"/>
                  <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow" result="shape"/>
                  </filter>
                  <linearGradient id="paint0_linear" x1="49.9392" y1="0.257812" x2="49.9392" y2="99.7423" gradientUnits="userSpaceOnUse">
                  <stop stop-color="white"/>
                  <stop offset="1" stop-color="white" stop-opacity="0"/>
                  </linearGradient>
                  </defs>
                  </svg>`
        },
        {
          name: 'GitHub',
          icon: `<svg class="w-5 h-5" viewBox="0 0 24 24" fill="currentColor" xmlns="http://www.w3.org/2000/svg"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>`
        },
        {
          name: 'Vue.js',
          icon: `<svg class="w-5 h-5" viewBox="0 0 256 221" xmlns="http://www.w3.org/2000/svg"><path d="M204.8 0H256L128 220.8L0 0h51.2L128 132.4L204.8 0z" fill="#41B883"/><path d="M51.2 0H128l76.8 0l-76.8 132.4L51.2 0z" fill="#35495E"/></svg>`
        },
        {
          name: 'Tailwind',
          icon: `<svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 4.8C9.2 4.8 7.5 6.2 6.7 9c1-1.4 2.2-2 3.6-1.7.8.2 1.4.7 2 1.3 1 1 2.2 2.2 4.8 2.2 2.8 0 4.5-1.4 5.3-4.2-1 1.4-2.2 2-3.6 1.7-.8-.2-1.4-.7-2-1.3-.9-1-2.2-2.2-4.8-2.2zm-6 6.6c-2.8 0-4.5 1.4-5.3 4.2 1-1.4 2.2-2 3.6-1.7.8.2 1.4.7 2 1.3 1 1 2.2 2.2 4.8 2.2 2.8 0 4.5-1.4 5.3-4.2-1 1.4-2.2 2-3.6 1.7-.8-.2-1.4-.7-2-1.3-.9-1-2.2-2.2-4.8-2.2z" fill="#06B6D4"/></svg>`
        },
        {
          name: 'Notion',
          icon: `<svg class="w-5 h-5" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M6.017 4.313l55.333 -4.087c6.797 -0.583 8.543 -0.19 12.817 2.917l17.663 12.443c2.913 2.14 3.883 2.723 3.883 5.053v68.243c0 4.277 -1.553 6.807 -6.99 7.193L24.467 99.967c-4.08 0.193 -6.023 -0.39 -8.16 -3.113L3.3 79.94c-2.333 -3.113 -3.3 -5.443 -3.3 -8.167V11.113c0 -3.497 1.553 -6.413 6.017 -6.8z" fill="#fff"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M61.35 0.227l-55.333 4.087C1.553 4.7 0 7.617 0 11.113v60.66c0 2.723 0.967 5.053 3.3 8.167l13.007 16.913c2.137 2.723 4.08 3.307 8.16 3.113l64.257 -3.89c5.433 -0.387 6.99 -2.917 6.99 -7.193V20.64c0 -2.21 -0.873 -2.847 -3.443 -4.733L74.167 3.143c-4.273 -3.107 -6.02 -3.5 -12.817 -2.917zM25.92 19.523c-5.247 0.353 -6.437 0.433 -9.417 -1.99L8.927 11.507c-0.77 -0.78 -0.383 -1.753 1.557 -1.947l53.193 -3.887c4.467 -0.39 6.793 1.167 8.54 2.527l9.123 6.61c0.39 0.197 1.36 1.36 0.193 1.36l-54.933 3.307 -0.68 0.047zM19.803 88.3V30.367c0 -2.53 0.777 -3.697 3.103 -3.893L86 22.78c2.14 -0.193 3.107 1.167 3.107 3.693v57.547c0 2.53 -0.39 4.67 -3.883 4.863l-60.377 3.5c-3.493 0.193 -5.043 -0.97 -5.043 -4.083zm59.6 -54.827c0.387 1.75 0 3.5 -1.75 3.7l-2.91 0.577v42.773c-2.527 1.36 -4.853 2.137 -6.797 2.137 -3.107 0 -3.883 -0.973 -6.21 -3.887l-19.03 -29.94v28.967l6.02 1.363s0 3.5 -4.857 3.5l-13.39 0.777c-0.39 -0.78 0 -2.723 1.357 -3.11l3.497 -0.97v-38.3L30.48 40.667c-0.39 -1.75 0.58 -4.277 3.3 -4.473l14.367 -0.967 19.8 30.327v-26.83l-5.047 -0.58c-0.39 -2.143 1.163 -3.7 3.103 -3.89l13.4 -0.78z" fill="#000"/></svg>`
        },
        {
          name: 'Canva',
          icon: `<svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="12" fill="url(#canva-grad)"/><path d="M12.2 16.5c-1.1 0-2.1-.3-2.9-1-.7-.6-1.1-1.5-1.1-2.6 0-1.1.4-2 1.1-2.6.8-.7 1.8-1 2.9-1 .8 0 1.6.2 2.2.6l.8-.9c-.8-.6-1.9-.9-3-.9-1.4 0-2.6.5-3.5 1.4-.9.9-1.4 2.1-1.4 3.5 0 1.4.5 2.6 1.4 3.5.9.9 2.1 1.4 3.5 1.4 1.2 0 2.2-.3 3-.9l-.8-1c-.6.4-1.4.6-2.2.6z" fill="white"/><defs><linearGradient id="canva-grad" x1="0" y1="0" x2="24" y2="24" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#00C4CC"/><stop offset="1" stop-color="#7D2AE8"/></linearGradient></defs></svg>`
        }
      ],

      softSkills: [
        'Problem Solving',
        'Team Collaboration',
        'Communication',
        'Time Management',
        'Creativity',
      ],
    }
  },

  mounted() {
    const observer = new IntersectionObserver(
      (entries) => {
        if (entries[0].isIntersecting) {
          setTimeout(() => {
            this.animated = true
          }, 200)
        }
      },
      { threshold: 0.3 }
    )

    observer.observe(this.$el)
  },
}
</script>


<template>
  <section id="skills">
    <div class="section-wrapper">

      <!-- Section Header -->
      <div class="reveal">
        <p class="section-subtitle">02 — Skills</p>
        <h2 class="section-title">What I Can Do</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-16 mt-12">

        <!-- Left: Skill Bars -->
        <div>
          <h3 class="reveal font-display text-xl text-gray-900 dark:text-white mb-6">
            Technical Skills
          </h3>

          <div class="space-y-5 ">
            <div v-for="(skill, index) in technicalSkills" :key="skill.name" class="reveal "
              :class="`reveal-delay-${index + 1}`">
              <div class="p-2 hover:-translate-y-1 transition-all duration-300 ease-out cursor-default group">
                <!-- Skill name + percentage -->
                <div class="flex justify-between items-center mb-2">
                  <span class="text-sm font-medium text-gray-700 dark:text-gray-300">
                    {{ skill.name }}
                  </span>
                  <span class="text-sm text-orange-500 font-medium">{{ skill.level }}%</span>
                </div>

                <!-- Progress bar track -->
                <div class="h-1.5 bg-gray-100 dark:bg-stone-800 rounded-full overflow-hidden">

                  <div
                    class="h-full bg-gradient-to-r from-orange-500 to-orange-400 rounded-full transition-all duration-1000 ease-out"
                    :style="{ width: animated ? skill.level + '%' : '0%' }"></div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="space-y-8">

          <!-- Tools & Technologies -->
          <div>
            <h3 class="reveal font-display text-xl text-gray-900 dark:text-white mb-6">
              Tools & Technologies
            </h3>
            <div class="grid grid-cols-3 gap-3">
              <div v-for="(tool, index) in tools" :key="tool.name" class="reveal"
                :class="`reveal-delay-${(index % 3) + 1}`">
                <div class="bg-gray-100 dark:bg-stone-800 border border-gray-100 dark:border-stone-700
                  rounded-2xl p-4 text-center
                  cursor-default group">

                  <div v-html="tool.icon"
                    class="flex justify-center mb-2 group-hover:scale-110 transition-transform duration-200">
                  </div>

                  <p class="text-xs text-gray-600 dark:text-gray-400 font-medium">{{ tool.name }}</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Soft Skills -->
          <div class="reveal">
            <h3 class="font-display text-xl text-gray-900 dark:text-white mb-4">Soft Skills</h3>
            <div class="flex flex-wrap gap-2">
              <span v-for="skill in softSkills" :key="skill" class="badge">{{ skill }}</span>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>