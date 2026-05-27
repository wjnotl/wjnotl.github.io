<script setup lang="ts">
import { ref } from 'vue'

interface Skill {
  title: string
  description: string
  icon: string
}

const skills = ref<Skill[]>([
  {
    title: 'Type Safety & Languages',
    description:
      'Writing strictly typed, predictable code using TypeScript to build robust applications and catch data errors early at compile time.',
    icon: 'bx bx-code'
  },
  {
    title: 'Backend & ORM Engineering',
    description:
      'Designing data layers and handling complex domain logic using modern development tools like Prisma ORM and Entity Framework Core (EF Core).',
    icon: 'bx bxs-dashboard'
  },
  {
    title: 'Database Management',
    description:
      'Structuring, optimizing, and querying relational data efficiently across engines including PostgreSQL, MySQL, and SQL Server.',
    icon: 'bx bxs-data'
  },
  {
    title: 'Scripting & Automation',
    description:
      'Writing custom automation routines to speed up development environments, parse packets, handle background tasks, and automate local workflows.',
    icon: 'bx bx-terminal'
  },
  {
    title: 'Git Version Control',
    description:
      'Managing source code securely using Git: tracking commits, managing branch strategy, creating PRs, and safely resolving complex merge conflicts.',
    icon: 'bx bxl-git'
  }
])
</script>

<template>
  <section class="w-full bg-[#252526] py-20 border-t border-b border-zinc-800">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-5xl font-bold mb-12 text-center text-white">
        My <span class="text-[#9cdcfe]">Skills</span>
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="(skill, idx) in skills"
          :key="idx"
          class="bg-[#1e1e1e] border-2 border-zinc-800 p-6 rounded-xl transition-all duration-500 hover:border-[#9cdcfe] hover:scale-[1.02] flex flex-col items-start text-left"
        >
          <div class="text-[#9cdcfe] mb-4">
            <i :class="[skill.icon, 'text-5xl']"></i>
          </div>
          <h3 class="text-2xl font-bold mb-2 text-white tracking-wide">{{ skill.title }}</h3>
          <p class="text-base text-gray-400 leading-relaxed max-w-sm">{{ skill.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>
