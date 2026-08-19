<template>
  <div class="min-h-screen bg-[#0B0F17] text-[#F3F4F6] flex flex-col font-sans">
    <Navbar />

    <main class="flex-grow">
      <HeroSection />
      <SkillsSection />
      <ExperienceSection />
      <ProjectsSection @open-modal="handleOpenModal" />
    </main>

    <FooterSection />

    <!-- Modal Flotante de Imágenes -->
    <ImageModal 
      :is-open="isModalOpen" 
      :project="selectedProject" 
      @close="isModalOpen = false" 
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import FooterSection from './components/FooterSection.vue'
import ImageModal from './components/ImageModal.vue'

const isModalOpen = ref(false)
const selectedProject = ref(null)

const handleOpenModal = (project) => {
  selectedProject.value = project
  isModalOpen.value = true
}
</script>
