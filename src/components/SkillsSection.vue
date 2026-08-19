<template>
  <section id="skills" class="py-20 bg-[#0B0F17]/50 border-t border-dark-border/40">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Encabezado de Sección -->
      <div class="mb-12">
        <div class="inline-flex items-center space-x-2 text-emerald-accent text-xs font-mono mb-2 uppercase tracking-widest">
          <Cpu class="w-4 h-4" />
          <span>Competencias Técnicas</span>
        </div>
        <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight">
          Habilidades & Herramientas
        </h2>
        <p class="text-gray-400 mt-2 max-w-2xl">
          Stack tecnológico enfocado en automatización, infraestructura como código, despliegues continuos y observabilidad.
        </p>
      </div>

      <!-- Grid de Categorías -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="category in skillCategories" 
          :key="category.title"
          class="bg-dark-card border border-dark-border rounded-xl p-6 hover:border-emerald-500/40 transition-all group"
        >
          <!-- Encabezado de Tarjeta -->
          <div class="flex items-center space-x-3 mb-5">
            <div class="p-2.5 rounded-lg bg-emerald-500/10 text-emerald-accent border border-emerald-500/20 group-hover:scale-105 transition-transform">
              <component :is="category.icon" class="w-5 h-5" />
            </div>
            <h3 class="font-semibold text-lg text-white">
              {{ category.title }}
            </h3>
          </div>

          <!-- Items de Skills (Formato código monospace) -->
          <div class="flex flex-wrap gap-2">
            <span 
              v-for="skill in category.skills" 
              :key="skill"
              class="code-badge px-3 py-1.5 rounded-md text-xs font-mono text-gray-300 flex items-center space-x-1.5"
            >
              <span class="text-emerald-accent font-bold">&gt;</span>
              <span>{{ skill }}</span>
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Cpu, Box, GitBranch, Layers, Cloud, Code } from 'lucide-vue-next'

const skillCategories = [
  {
    title: 'Desarrollo Frontend',
    icon: Code,
    skills: ['Vue.js (Vue 3)', 'HTML5', 'CSS3', 'Vuetify', 'Tailwind CSS']
  },
  {
    title: 'Desarrollo Backend',
    icon: Layers,
    skills: ['PHP', 'Laravel', 'PostgreSQL', 'MySQL', 'REST APIs', 'SQL']
  },
  {
    title: 'Contenedores y Orquestación',
    icon: Box,
    skills: ['Docker', 'Docker Compose', 'Kubernetes', 'Helm']
  },
  {
    title: 'CI/CD & Automatización',
    icon: GitBranch,
    skills: ['GitHub Actions', 'GHCR', 'Git/GitHub']
  },
  {
    title: 'Infraestructura & Cloud',
    icon: Cloud,
    skills: ['Terraform', 'Microsoft Azure', 'IaC', 'Redes']
  },
  {
    title: 'Habilidades Blandas',
    icon: Cpu,
    skills: ['Trabajo en equipo', 'Resolución de problemas', 'Comunicación', 'Organización']
  }
]
</script>
