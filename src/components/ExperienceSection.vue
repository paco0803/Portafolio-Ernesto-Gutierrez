<template>
  <section id="experiencia" class="py-20 border-t border-dark-border/40 bg-[#0B0F17]/50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header de la sección -->
      <div class="mb-12">
        <div class="inline-flex items-center space-x-2 text-emerald-accent text-xs font-mono mb-2 uppercase tracking-widest">
          <Briefcase class="w-4 h-4" />
          <span>Trayectoria</span>
        </div>
        <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight">
          Experiencia Laboral
        </h2>
      </div>

      <!-- Lista de Experiencias -->
      <div class="space-y-8">
        <div 
          v-for="exp in experiences" 
          :key="exp.id"
          class="bg-dark-card border border-dark-border rounded-2xl p-6 sm:p-8 hover:border-emerald-500/40 transition-all group"
        >
          <div class="flex flex-col md:flex-row md:items-center justify-between mb-4">
            <div>
              <h3 class="text-2xl font-bold text-white group-hover:text-emerald-accent transition-colors">
                {{ exp.role }}
              </h3>
              <p class="text-lg text-gray-300 font-medium mt-1">{{ exp.company }}</p>
            </div>
            <div class="mt-2 md:mt-0 px-4 py-1.5 rounded-full bg-emerald-500/10 border border-emerald-500/20 text-emerald-accent text-sm font-mono inline-block text-center self-start md:self-center">
              {{ exp.period }}
            </div>
          </div>

          <p class="text-gray-400 text-sm leading-relaxed mb-6">
            {{ exp.description }}
          </p>

          <!-- Highlights -->
          <div class="space-y-3 mb-6">
            <div v-for="highlight in exp.highlights" :key="highlight" class="flex items-start space-x-3 text-sm text-gray-300">
              <CheckCircle2 class="w-5 h-5 text-emerald-accent flex-shrink-0" />
              <span>{{ highlight }}</span>
            </div>
          </div>

          <!-- Píldoras de Tecnologías -->
          <div class="flex flex-wrap gap-2 pt-4 border-t border-dark-border/60">
            <span 
              v-for="tech in exp.technologies" 
              :key="tech"
              class="px-2.5 py-1 text-xs font-mono rounded bg-dark-bg border border-dark-border text-gray-400 group-hover:text-gray-300 transition-colors"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Briefcase, CheckCircle2 } from 'lucide-vue-next'

const experiences = [
  {
    id: 'naviarca',
    role: 'Pasante de Ingeniería de Sistemas',
    company: 'Naviarca | Cumaná, Estado Sucre',
    period: 'Febrero 2026 - Mayo 2026',
    description: 'Diseño y desarrollo de un módulo administrativo web para la gestión de compras del sistema corporativo SISOPEP, optimizando los flujos operativos del departamento.',
    highlights: [
      'Implementación de una arquitectura moderna y escalable utilizando Vue 3, Laravel y PostgreSQL.',
      'Sustitución de procesos manuales y dependencias de software obsoleto (Profit Plus) mediante el desarrollo de interfaces SPA dinámicas con Vuetify, mejorando la eficiencia y la UX del personal administrativo.',
      'Diseño de la arquitectura de la base de datos relacional y modelado del comportamiento del sistema utilizando estándares UML (Casos de uso, Secuencia, Clases, Estados).'
    ],
    technologies: ['Vue 3', 'Laravel', 'PostgreSQL', 'Vuetify', 'UML']
  }
]
</script>
