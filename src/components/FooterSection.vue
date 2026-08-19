<template>
  <footer id="contacto" class="py-16 bg-[#080B11] border-t border-dark-border">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center justify-between">
        <!-- Izquierda: Información de Contacto y Perfil -->
        <div>
          <div class="flex items-center space-x-2 mb-3">
            <div class="w-7 h-7 rounded bg-emerald-500/10 border border-emerald-500/30 flex items-center justify-center text-emerald-accent font-mono font-bold text-xs">
              &gt;_
            </div>
            <span class="font-mono font-bold text-lg text-white">
              Ernesto Gutierrez
            </span>
          </div>
          <p class="text-gray-400 text-sm max-w-md leading-relaxed">
            Ingeniero de Sistemas orientado al desarrollo web, operaciones cloud y cultura DevOps.
          </p>
        </div>

        <!-- Derecha: Redes Sociales & Enlaces Directos -->
        <div class="flex flex-wrap items-center md:justify-end gap-4">
          <a 
            href="https://www.linkedin.com/in/ernesto-gutierrez-28abb0311" 
            target="_blank" 
            rel="noopener noreferrer"
            class="p-3 rounded-xl bg-dark-card border border-dark-border text-gray-400 hover:text-emerald-accent hover:border-emerald-500/40 transition-all group"
            title="LinkedIn"
          >
            <Linkedin class="w-5 h-5 group-hover:scale-110 transition-transform" />
          </a>

          <a 
            href="https://github.com/paco0803?tab=repositories" 
            target="_blank" 
            rel="noopener noreferrer"
            class="p-3 rounded-xl bg-dark-card border border-dark-border text-gray-400 hover:text-emerald-accent hover:border-emerald-500/40 transition-all group"
            title="GitHub"
          >
            <Github class="w-5 h-5 group-hover:scale-110 transition-transform" />
          </a>

          <a 
            href="https://mail.google.com/mail/?view=cm&fs=1&to=ernestogutierrez0803@gmail.com" 
            target="_blank"
            rel="noopener noreferrer"
            class="p-3 rounded-xl bg-dark-card border border-dark-border text-gray-400 hover:text-emerald-accent hover:border-emerald-500/40 transition-all group"
            title="Correo Electrónico"
          >
            <Mail class="w-5 h-5 group-hover:scale-110 transition-transform" />
          </a>
        </div>
      </div>

      <div class="mt-12 pt-8 border-t border-dark-border/60 flex flex-col md:flex-row items-center justify-between gap-4">
        <p class="text-sm text-gray-500 font-mono">
          © 2026 Ernesto Gutierrez. Todos los derechos reservados.
        </p>

        <a 
          :href="`${baseUrl}CV_Ernesto_Gutierrez.pdf`"
          download="CV_Ernesto_Gutierrez.pdf"
          class="inline-flex items-center space-x-2 px-4 py-2 rounded-lg bg-emerald-500/10 text-emerald-accent border border-emerald-500/30 hover:bg-emerald-500 hover:text-black transition-all font-mono text-sm"
        >
          <Download class="w-4 h-4" />
          <span>Descargar CV Completo</span>
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { Github, Linkedin, Mail, Download } from 'lucide-vue-next'

const baseUrl = import.meta.env.BASE_URL
</script>
