<script setup lang="ts">
import HeroSection from '@/components/HeroSection.vue'
import SkillsSection from '@/components/SkillsSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue'
</script>

<template>
  <div
    class="min-h-screen text-[#d4d4d4] selection:bg-[#9cdcfe] selection:text-[#1e1e1e] font-mono text-base"
  >
    <HeroSection />
    <SkillsSection />
    <ProjectsSection />

    <footer
      class="w-full bg-[#171717] py-10 text-center text-sm text-zinc-500 border-t border-zinc-800"
    >
      &copy; {{ new Date().getFullYear() }} Liew Wen Jing. All rights reserved.
    </footer>
  </div>
</template>
