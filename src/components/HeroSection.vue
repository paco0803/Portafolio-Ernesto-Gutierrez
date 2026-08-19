<template>
  <section id="inicio" class="relative pt-32 pb-20 md:pt-40 md:pb-28 overflow-hidden">
    <!-- Grid Background Glow -->
    <div class="absolute inset-0 bg-[linear-gradient(to_right,#1F293715_1px,transparent_1px),linear-gradient(to_bottom,#1F293715_1px,transparent_1px)] bg-[size:4rem_4rem] [mask-image:radial-gradient(ellipse_60%_50%_at_50%_0%,#000_70%,transparent_100%)] pointer-events-none"></div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="flex flex-col-reverse lg:flex-row items-center gap-12">
        
        <!-- Texto y Contenido -->
        <div class="flex-1 lg:max-w-3xl text-left">
          <!-- Badge de Disponibilidad -->
          <div class="inline-flex items-center space-x-2 px-3 py-1.5 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-accent text-xs font-mono mb-6">
            <span class="relative flex h-2 w-2">
              <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
              <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
            </span>
            <span>Ernesto Gutierrez | Ingeniero de Sistemas</span>
          </div>

          <!-- Título Principal -->
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-white leading-tight mb-6">
            Ingeniería de Sistemas orientada a <span class="bg-gradient-to-r from-emerald-400 via-cyan-400 to-blue-500 bg-clip-text text-transparent">DevOps, Cloud & Desarrollo Web</span>
          </h1>

          <!-- Subtítulo / Descripción Profesional -->
          <p class="text-lg sm:text-xl text-gray-400 leading-relaxed mb-8">
            Egresado de Ingeniería de Sistemas (UGMA) entusiasta de la <strong class="text-gray-200">cultura DevOps, operaciones en la nube y el desarrollo web moderno</strong>. Cuento con bases sólidas en Vue.js, Laravel, Docker, Kubernetes y Terraform, lo que me permite tender un puente efectivo entre el código y su paso a producción.
          </p>

          <!-- Botones CTA -->
          <div class="flex flex-wrap items-center gap-4 mb-12">
            <a 
              :href="`${baseUrl}CV_Ernesto_Gutierrez.pdf`"
              download="CV_Ernesto_Gutierrez.pdf"
              class="inline-flex items-center space-x-2 px-6 py-3 rounded-xl bg-emerald-500 text-black font-semibold hover:bg-emerald-400 transition-all shadow-[0_0_20px_rgba(16,185,129,0.3)]"
            >
              <Download class="w-5 h-5" />
              <span>Descargar CV (PDF)</span>
            </a>

            <a 
              href="#proyectos" 
              class="inline-flex items-center space-x-2 px-6 py-3 rounded-xl bg-dark-card border border-dark-border text-gray-300 font-medium hover:text-white hover:border-gray-600 transition-all"
            >
              <FolderGit2 class="w-5 h-5 text-emerald-accent" />
              <span>Explorar Proyectos</span>
            </a>
          </div>

          <!-- Badges de Destacados Técnicos -->
          <div class="pt-6 border-t border-dark-border/60">
            <p class="text-xs font-mono text-gray-500 uppercase tracking-widest mb-4">Core Tech Stack</p>
            <div class="flex flex-wrap gap-2">
              <span v-for="tech in coreStack" :key="tech" class="px-3 py-1 text-xs font-mono rounded-md bg-dark-card border border-dark-border text-gray-300 flex items-center space-x-1.5">
                <Terminal class="w-3.5 h-3.5 text-emerald-accent" />
                <span>{{ tech }}</span>
              </span>
            </div>
          </div>
        </div>

        <!-- Foto de Perfil (Rectángulo redondeado a la derecha) -->
        <div class="flex-1 w-full flex justify-center lg:justify-end">
          <div class="relative w-full max-w-sm lg:max-w-md aspect-[3/4] rounded-3xl overflow-hidden border-2 border-dark-border shadow-[0_0_40px_rgba(16,185,129,0.15)]">
            <img :src="`${baseUrl}profile.jpg`" alt="Ernesto Gutierrez" class="w-full h-full object-cover object-top" />
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { Download, FolderGit2, Terminal } from 'lucide-vue-next'

const coreStack = ['Vue.js', 'Laravel', 'Docker & Kubernetes', 'Terraform', 'GitHub Actions', 'Microsoft Azure', 'PostgreSQL']
const baseUrl = import.meta.env.BASE_URL
</script>
