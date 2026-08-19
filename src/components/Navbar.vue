<template>
  <header class="fixed top-0 left-0 right-0 z-50 bg-[#0B0F17]/80 backdrop-blur-md border-b border-dark-border/60">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
      <!-- Logo -->
      <a href="#inicio" class="flex items-center space-x-2 group">
        <div class="w-8 h-8 rounded-lg bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center text-emerald-accent font-mono font-bold group-hover:border-emerald-500 group-hover:bg-emerald-500/20 transition-all">
          &gt;_
        </div>
        <span class="font-mono font-semibold text-lg text-white tracking-wide">
          Ernesto<span class="text-emerald-accent">.</span>G
        </span>
      </a>

      <!-- Desktop Nav Enlaces -->
      <nav class="hidden md:flex items-center space-x-8 text-sm font-medium text-gray-300">
        <a href="#inicio" class="hover:text-emerald-accent transition-colors">Inicio</a>
        <a href="#skills" class="hover:text-emerald-accent transition-colors">Skills</a>
        <a href="#experiencia" class="hover:text-emerald-accent transition-colors">Experiencia</a>
        <a href="#proyectos" class="hover:text-emerald-accent transition-colors">Proyectos</a>
        <a href="#contacto" class="hover:text-emerald-accent transition-colors">Contacto</a>
      </nav>

      <!-- CTA Botón CV -->
      <div class="flex items-center space-x-4">
        <a 
          :href="`${import.meta.env.BASE_URL}CV_Ernesto_Gutierrez.pdf`"
          download="CV_Ernesto_Gutierrez.pdf"
          class="inline-flex items-center space-x-2 px-4 py-2 rounded-lg bg-emerald-500/10 text-emerald-accent border border-emerald-500/30 hover:bg-emerald-500 hover:text-black transition-all font-mono text-sm"
        >
          <Download class="w-4 h-4" />
          <span>Descargar CV</span>
        </a>
      </div>
    </div>
  </header>
</template>

<script setup>
import { Download } from 'lucide-vue-next'
</script>
