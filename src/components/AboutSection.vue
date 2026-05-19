<script>
export default {
  name: 'AboutSection',

  data() {
    return {
      quickInfo: [
        { label: 'Location',   value: 'Bangkok, Thailand' },
        { label: 'University', value: 'King Mongkut University of Technology Thonburi' },
        { label: 'Year',       value: '2nd Year Student' },
        { label: 'Focus',      value: 'UX Design & Frontend' },
      ],

      education: [
        {
          year:   '2024 – Present',
          degree: 'School of Information Technology',
          school: 'King Mongkut University of Technology Thonburi',
        },
        {
          year:   '2021 – 2024',
          degree: 'Gifted Sci-Math-Eng',
          school: 'Matthayom Wat Nongkhaem School',
        },
      ],

      interests: [
        'UX Design',
        'Frontend',
        'Open Source',
        'Cars',
        'Motorbike',    
      ],
    }
  },
}
</script>

<template>
  <section id="about" class="bg-orange-50 dark:bg-stone-900 transition-colors duration-300">
    <div class="section-wrapper">

      <div class="reveal">
        <p class="section-subtitle">01 — About</p>
        <h2 class="section-title">Who I Am</h2>
      </div>

      <div class="grid md:grid-cols-2 gap-16 items-start mt-12">

        <div class="reveal reveal-delay-1 space-y-5 text-gray-600 dark:text-gray-400 leading-relaxed">
          <p>
            Hi there! I’m an Information Technology student at SIT, KMUTT. While studying the technical side of IT, 
            I discovered a real enjoyment for UX design and frontend development. I don’t see myself as an expert, 
            but I’m someone who simply loves trying to make digital spaces look a bit friendlier and feel easier for people to use.
          </p>
          <p>
            As a visual learner, I spend a lot of my free time watching video tutorials, UI/UX breakdowns, and tech vlogs to pick up new concepts.
            Right now, I’m focused on practicing how to design clean layouts and bringing them to life using Vue.js and Tailwind CSS. 
            I’m still learning and figuring things out every day, but I genuinely enjoy the process of practicing and fixing bugs.
          </p>
          <p>
            When I’m not sketching wireframes or tweaking code, you’ll probably find me watching videos about cars and motorbikes,
            or exploring open-source projects. I’m currently looking for a supportive internship opportunity where I can learn from 
            experienced people, help out with real tasks, and grow my skills as a designer.
          </p>
        </div>

        <div class="space-y-8">

          <div class="reveal reveal-delay-2">
            <h3 class="font-display text-xl text-gray-900 dark:text-white mb-4">Education</h3>
            <div
              v-for="edu in education"
              :key="edu.school"
              class="relative pl-6 pb-6 border-l-2 border-orange-500/20 last:border-transparent"
            >
              <div class="absolute -left-1.5 top-1 w-3 h-3 rounded-full bg-orange-500"></div>
              <p class="text-sm text-orange-500 font-medium">{{ edu.year }}</p>
              <p class="font-medium text-gray-900 dark:text-white">{{ edu.degree }}</p>
              <p class="text-sm text-gray-500 dark:text-gray-400">{{ edu.school }}</p>
            </div>
          </div>

          <div class="reveal reveal-delay-3">
            <h3 class="font-display text-xl text-gray-900 dark:text-white mb-4">Interests</h3>
            <div class="flex flex-wrap gap-2">
              <span v-for="interest in interests" :key="interest" class="badge">
                {{ interest }}
              </span>
            </div>
          </div>

          <div class="reveal reveal-delay-4">
            <div class="grid grid-cols-2 gap-4">
              <div
                v-for="info in quickInfo"
                :key="info.label"
                class="bg-white dark:bg-stone-800 rounded-2xl p-4 border border-gray-100 dark:border-stone-700"
              >
                <p class="text-xs text-gray-400 dark:text-gray-500 mb-1">{{ info.label }}</p>
                <p class="text-sm font-medium text-gray-900 dark:text-white">{{ info.value }}</p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

