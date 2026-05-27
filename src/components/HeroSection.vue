<script setup lang="ts">
import { ref, onMounted } from 'vue'

const titles: string[] = [
  'Web Developer',
  'Game Developer',
  'Database Designer',
  'Userscript Developer'
]

const currentTitle = ref<string>('')
const titleIdx = ref<number>(0)
const charIdx = ref<number>(0)
const isDeleting = ref<boolean>(false)

const socialItems = [
  { link: 'https://wjnotl.github.io', icon: 'bx bx-globe' },
  { link: 'https://greasyfork.org/en/users/999838', icon: 'bx bx-fork' },
  { link: 'https://github.com/wjnotl', icon: 'bx bxl-github' },
  { link: 'https://github.com/kookywarrior', icon: 'bx bx-joystick' },
  { link: 'mailto:liewwenjing34882@gmail.com', icon: 'bx bx-at' }
]

function typeEffect(): void {
  const currentFullText = titles[titleIdx.value] || ''

  if (isDeleting.value) {
    currentTitle.value = currentFullText.substring(0, charIdx.value - 1)
    charIdx.value--
  } else {
    currentTitle.value = currentFullText.substring(0, charIdx.value + 1)
    charIdx.value++
  }

  let typeSpeed = isDeleting.value ? 40 : 80

  if (!isDeleting.value && currentTitle.value === currentFullText) {
    typeSpeed = 1200
    isDeleting.value = true
  } else if (isDeleting.value && currentTitle.value === '') {
    isDeleting.value = false
    titleIdx.value = (titleIdx.value + 1) % titles.length
    typeSpeed = 400
  }

  setTimeout(typeEffect, typeSpeed)
}

onMounted(() => {
  typeEffect()
})
</script>

<template>
  <header class="w-full min-h-screen flex items-center bg-[#1e1e1e]">
    <div class="max-w-6xl w-full mx-auto px-6 text-left">
      <h3 class="text-3xl font-bold text-white mb-2">Hello, my name is</h3>
      <h1 class="text-[4rem] leading-tight font-bold tracking-tight text-white mb-4">
        Liew Wen Jing
      </h1>

      <h3 class="text-3xl font-bold text-white mb-6 flex items-center h-10">
        And I'm a&nbsp;
        <span
          class="text-[#9cdcfe] border-r-3 border-[#9cdcfe] pr-1 inline-block h-full leading-10"
        >
          {{ currentTitle }}
        </span>
      </h3>

      <p class="text-xl text-gray-400 leading-relaxed">
        A passionate developer with experience in web development, game development, and advanced
        scripting. I enjoy exploring creative ways to solve problems, automate tasks, and design
        efficient solutions.
      </p>

      <div class="flex flex-wrap gap-4 mt-8">
        <a
          v-for="(social, index) in socialItems"
          :key="index"
          :href="social.link"
          target="_blank"
          class="inline-flex justify-center items-center w-11 h-11 rounded-full border-2 border-[#9cdcfe] text-[#9cdcfe] transition-all duration-300 hover:scale-110 hover:-translate-y-1.5 hover:bg-[#9cdcfe] hover:text-[#1e1e1e]"
        >
          <i :class="[social.icon, 'text-xl']"></i>
        </a>
      </div>
    </div>
  </header>
</template>
