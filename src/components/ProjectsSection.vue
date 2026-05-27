<script setup lang="ts">
import { ref } from 'vue'

interface Project {
  title: string
  description: string
  technologies: string
  image: string
  link: string
}

const projects = ref<Project[]>([
  {
    title: 'Cinema Ticketing System',
    description: 'Web app for movie booking, showtime scheduling, f&b order, and seat management.',
    technologies: 'ASP.NET C#, MS SQL Server, jQuery',
    image: './img/cinema-ticketing-system.jpeg',
    link: 'https://github.com/wjnotl/cinema-ticketing-system'
  },
  {
    title: 'Grid War',
    description:
      'A real-time online multiplayer strategy survival game based on the legendary 2048 game.',
    technologies: 'Node.js, WebSocket, Canvas',
    image: './img/grid-war.jpeg',
    link: 'https://github.com/kookywarrior/grid-war'
  },
  {
    title: 'E-commerce System',
    description:
      'An online shopping platform with product management, advance searching and filtering, cart and order management features.',
    technologies: 'PHP, MySQL, jQuery',
    image: './img/e-commerce-system.jpeg',
    link: 'https://github.com/wjnotl/e-commerce-system'
  },
  {
    title: 'Jscrambler Code Deobfuscator',
    description:
      'A tool to reverse bonk.io obfuscated source code which is based on Jscrambler via AST analysis.',
    technologies: 'Node.js, acorn walk, Deep clone objects',
    image: './img/deobfuscator.jpeg',
    link: 'https://github.com/kookywarrior/bonk-deobfuscator'
  },
  {
    title: 'Student Toolkit App',
    description:
      'An application for students which includes study forums, reminders, and feature to calculate and store grades.',
    technologies: 'Python, Plyer, Custom TKinter',
    image: './img/student-toolkit-app.jpeg',
    link: 'https://github.com/wjnotl/software-development-fundamentals'
  },
  {
    title: 'Game Private Server',
    description:
      'A setup for hosting a private game server, allowing custom game modes and private matches with friends.',
    technologies: 'Node.js, WebSocket',
    image: './img/game-private-server.jpeg',
    link: 'https://github.com/kookywarrior/moomooio-private-server'
  },
  {
    title: 'In Game Recorder',
    description:
      'A tool to record gameplay by capturing user input and websocket data, and re-render the gameplay in canvas.',
    technologies: 'Node.js, WebSocket, ExpressJS, FFmpeg, Canvas',
    image: './img/ingame-recorder.jpeg',
    link: 'https://github.com/kookywarrior/moomooio-recorder'
  },
  {
    title: 'Game Asset Toolkit',
    description:
      'A collection of game object images with a simple web interface, useful for creating thumbnails or game-related visuals.',
    technologies: 'Canvas, HTML, CSS',
    image: './img/game-asset-toolkit.jpeg',
    link: 'https://github.com/kookywarrior/moomoo-elements'
  }
])
</script>

<template>
  <section class="w-full bg-[#1e1e1e] py-20">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-5xl font-bold mb-12 text-center text-white">
        My <span class="text-[#9cdcfe]">Projects</span>
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(project, idx) in projects"
          :key="idx"
          class="bg-[#252526] border-2 border-zinc-800 rounded-xl overflow-hidden flex flex-col justify-between text-left transition-all duration-500 hover:border-[#9cdcfe] hover:scale-[1.02]"
        >
          <div>
            <div class="w-full overflow-hidden relative">
              <img :src="project.image" :alt="project.title" class="w-full object-cover" />
            </div>
            <div class="p-5">
              <h3 class="text-xl font-bold text-white mb-2 tracking-wide">{{ project.title }}</h3>
              <p class="text-base text-gray-400 leading-relaxed mb-4 min-h-12">
                {{ project.description }}
              </p>
              <p class="text-base text-gray-400 font-medium tracking-wide">
                Technologies:
                <span class="text-[#9cdcfe] font-normal text-base">{{ project.technologies }}</span>
              </p>
            </div>
          </div>

          <div class="px-5 pb-5 mt-2">
            <a
              :href="project.link"
              target="_blank"
              class="inline-block text-center px-6 py-2.5 rounded-full bg-[#9cdcfe] text-[#1e1e1e] text-sm font-semibold tracking-wide transition-all duration-300 hover:bg-[#82cbef]"
            >
              See Project
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
