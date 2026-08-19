<template>
  <Teleport to="body">
    <div 
      v-if="isOpen && project" 
      class="fixed inset-0 z-50 flex items-center justify-center p-4 sm:p-6 lg:p-8 bg-black/80 backdrop-blur-md transition-opacity"
      @click.self="close"
    >
      <div class="bg-dark-card border border-dark-border rounded-2xl max-w-5xl w-full max-h-[90vh] overflow-hidden flex flex-col shadow-2xl relative animate-in fade-in zoom-in duration-200">
        <!-- Modal Header -->
        <div class="px-6 py-4 border-b border-dark-border/60 flex items-center justify-between bg-[#0B0F17]/80">
          <div>
            <span class="text-xs font-mono text-emerald-accent uppercase tracking-wider">{{ project.category }}</span>
            <h4 class="text-lg font-bold text-white">{{ project.title }}</h4>
          </div>
          <button 
            @click="close"
            class="p-2 rounded-lg bg-dark-bg text-gray-400 hover:text-white hover:bg-dark-border transition-all"
          >
            <X class="w-5 h-5" />
          </button>
        </div>

        <!-- Modal Body (Imagen ampliada) -->
        <div class="p-6 overflow-y-auto space-y-6">
          <div class="rounded-xl overflow-hidden border border-dark-border/80 bg-black">
            <img :src="project.image" :alt="project.title" class="w-full h-auto object-contain max-h-[60vh]" />
          </div>

          <div class="space-y-4">
            <h5 class="text-sm font-mono text-emerald-accent uppercase tracking-wider">Detalles Técnicos & Resultados</h5>
            <p class="text-gray-300 text-sm leading-relaxed">{{ project.description }}</p>
            
            <div class="flex flex-wrap gap-2 pt-2">
              <span 
                v-for="tech in project.technologies" 
                :key="tech"
                class="code-badge px-2.5 py-1 text-xs font-mono text-gray-300 rounded"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>

        <!-- Modal Footer -->
        <div class="px-6 py-4 border-t border-dark-border/60 bg-[#0B0F17]/80 flex items-center justify-end space-x-3">
          <a 
            :href="project.githubUrl" 
            target="_blank" 
            rel="noopener noreferrer"
            class="inline-flex items-center space-x-2 px-4 py-2 text-xs font-mono font-semibold rounded-lg bg-emerald-500 text-black hover:bg-emerald-400 transition-all"
          >
            <Github class="w-4 h-4" />
            <span>Ver Repositorio en GitHub</span>
          </a>
          <button 
            @click="close" 
            class="px-4 py-2 text-xs font-mono rounded-lg bg-dark-bg border border-dark-border text-gray-300 hover:text-white transition-all"
          >
            Cerrar
          </button>
        </div>
      </div>
    </div>
  </Teleport>
</template>

<script setup>
import { X, Github } from 'lucide-vue-next'

const props = defineProps({
  isOpen: Boolean,
  project: Object
})

const emit = defineEmits(['close'])

const close = () => {
  emit('close')
}
</script>
