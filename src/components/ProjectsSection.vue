<template>
  <section id="proyectos" class="py-20 border-t border-dark-border/40">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header de la sección -->
      <div class="mb-12 flex flex-col md:flex-row md:items-end justify-between">
        <div>
          <div class="inline-flex items-center space-x-2 text-emerald-accent text-xs font-mono mb-2 uppercase tracking-widest">
            <FolderGit2 class="w-4 h-4" />
            <span>Casos de Estudio</span>
          </div>
          <h2 class="text-3xl sm:text-4xl font-bold text-white tracking-tight">
            Proyectos Destacados
          </h2>
          <p class="text-gray-400 mt-2 max-w-2xl">
            Implementaciones prácticas documentadas con repositorios en GitHub, diagramas de arquitectura y métricas en tiempo real.
          </p>
        </div>
      </div>

      <!-- Lista de Proyectos -->
      <div class="space-y-12">
        <div 
          v-for="project in projects" 
          :key="project.id"
          class="bg-dark-card border border-dark-border rounded-2xl overflow-hidden hover:border-emerald-500/40 transition-all grid grid-cols-1 lg:grid-cols-12 gap-0 group"
        >
          <!-- Vista Previa de Imagen / Dashboard -->
          <div class="lg:col-span-6 relative overflow-hidden bg-black/40 min-h-[260px] flex items-center justify-center transition-all">
            <img 
              :src="project.image" 
              :alt="project.title" 
              class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-dark-card via-transparent to-transparent opacity-60"></div>
          </div>

          <!-- Detalles del Proyecto -->
          <div class="lg:col-span-6 p-6 sm:p-8 flex flex-col justify-between">
            <div>
              <div class="flex items-center space-x-2 text-xs font-mono text-emerald-accent mb-2">
                <span>{{ project.category }}</span>
              </div>

              <h3 class="text-2xl font-bold text-white mb-3 group-hover:text-emerald-accent transition-colors">
                {{ project.title }}
              </h3>

              <p class="text-gray-300 text-sm leading-relaxed mb-6">
                {{ project.description }}
              </p>

              <!-- Highlights Clave -->
              <div class="mb-6 space-y-2">
                <div v-for="highlight in project.highlights" :key="highlight" class="flex items-start space-x-2 text-xs text-gray-400">
                  <CheckCircle2 class="w-4 h-4 text-emerald-accent flex-shrink-0 mt-0.5" />
                  <span>{{ highlight }}</span>
                </div>
              </div>

              <!-- Píldoras de Tecnologías -->
              <div class="flex flex-wrap gap-2 mb-8">
                <span 
                  v-for="tech in project.technologies" 
                  :key="tech"
                  class="px-2.5 py-1 text-xs font-mono rounded bg-dark-bg border border-dark-border text-gray-300"
                >
                  {{ tech }}
                </span>
              </div>
            </div>

            <!-- Botones de Acción -->
            <div class="flex items-center space-x-4 pt-4 border-t border-dark-border/60">
              <a 
                v-if="project.githubUrl"
                :href="project.githubUrl" 
                target="_blank" 
                rel="noopener noreferrer"
                class="inline-flex items-center space-x-2 px-4 py-2 text-xs font-mono font-medium rounded-lg bg-emerald-500 text-black hover:bg-emerald-400 transition-all font-semibold"
              >
                <Github class="w-4 h-4" />
                <span>Ver Código en GitHub</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { FolderGit2, CheckCircle2, Github } from 'lucide-vue-next'

const projects = [

  {
    id: 'cloud-migration',
    category: 'DevOps & Cloud Computing',
    title: 'Migración End-to-End y Automatización Cloud',
    description: 'Migración de un proyecto universitario a una arquitectura escalable en la nube utilizando prácticas y herramientas DevOps.',
    highlights: [
      'Implementación de pipelines CI/CD automatizados en GitHub Actions para análisis de código (PHPStan), construcción y publicación en GHCR.',
      'Configuración de despliegues dinámicos y gestión centralizada con Kubernetes y Helm Charts.',
      'Aprovisionamiento de infraestructura como código (IaC) en Microsoft Azure (VNets, Firewalls, VMs Linux) mediante Terraform.'
    ],
    technologies: ['Terraform', 'Azure', 'Kubernetes', 'Helm', 'Docker', 'GitHub Actions', 'CI/CD'],
    image: '/migration.png',
    githubUrl: 'https://github.com/paco0803/proyecto-universitario-end-to-end'
  },
  {
    id: 'mlops-deployment',
    category: 'MLOps & Inteligencia Artificial',
    title: 'Despliegue y Monitoreo de Modelo de IA',
    description: 'Despliegue integral de un modelo de machine learning en producción, asegurando su escalabilidad y observabilidad.',
    highlights: [
      'Puesta en producción de un modelo de IA integrando buenas prácticas.',
      'Creación de una API robusta para servir predicciones.',
      'Implementación de observabilidad y métricas de rendimiento.'
    ],
    technologies: ['Python', 'Docker', 'Machine Learning', 'API', 'Monitoreo'],
    image: '/monitoreo.jpg',
    githubUrl: 'https://github.com/paco0803/Despliegue-y-Monitoreo-de-un-Modelo-de-IA'
  },
  {
    id: 'nitrogenium',
    category: 'Desarrollo de Software (.NET)',
    title: 'Sistema de Administración Interna - Nitrogenium',
    description: 'Desarrollo de un sistema en C# para la administración interna de una empresa distribuidora de nitrógeno. Desarrollado con asistencia de Inteligencia Artificial para aplicar buenas prácticas de ingeniería.',
    highlights: [
      'Asistencia de IA (Agentes) estructurada con un criterio sólido para asegurar un diseño limpio y escalable.',
      'Implementación de patrones de diseño y clean architecture.',
      'Desarrollo y gestión eficiente de la base de datos y flujos de negocio.'
    ],
    technologies: ['C#', '.NET', 'AI Assisted', 'Clean Code'],
    image: 'https://images.unsplash.com/photo-1517048676732-d65bc937f952?ixlib=rb-4.0.3&auto=format&fit=crop&w=1170&q=80',
    githubUrl: 'https://github.com/paco0803/proyecto_nitrogenium'
  },
  {
    id: 'portfolio',
    category: 'Desarrollo Web (Frontend)',
    title: 'Portafolio Profesional Personal',
    description: 'Este mismo portafolio, creado como demostración de mis habilidades. Fue desarrollado de la mano con Inteligencia Artificial utilizando técnicas de prompt engineering y arquitectura de componentes.',
    highlights: [
      'Uso de agentes de IA para acelerar el desarrollo garantizando buenas prácticas y un código limpio.',
      'Diseño moderno, responsive y dinámico con Vue 3 y Tailwind CSS.',
      'Estructurado para un despliegue rápido y escalabilidad.'
    ],
    technologies: ['Vue 3', 'Tailwind CSS', 'Vite', 'AI Assisted'],
    image: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1170&q=80',
    githubUrl: 'https://github.com/paco0803'
  }
]
</script>
