<script setup>
import { useRoute } from "vue-router";
import ThemeToggle from "./components/ThemeToggle.vue";

const route = useRoute();
</script>

<template>
  <div class="min-h-screen bg-slate-100 dark:bg-slate-900 transition-colors">
    <div class="max-w-7xl mx-auto px-4 py-6">
      <!-- Header -->
      <header class="flex items-center justify-between mb-4">
        <h1 class="text-xl font-semibold text-slate-800 dark:text-slate-100">
          Tibetan Mantra to IAST and Phonetics
        </h1>
        <ThemeToggle />
      </header>

      <!-- Navigation Tabs -->
      <nav
        v-if="route.name !== 'tests'"
        class="flex border-b border-slate-200 dark:border-slate-700 mb-6"
      >
        <router-link
          to="/"
          class="px-6 py-3 text-sm font-medium transition-colors border-b-2 -mb-px"
          :class="
            route.name === 'convert'
              ? 'border-indigo-600 text-indigo-600 dark:text-indigo-400'
              : 'border-transparent text-slate-500 dark:text-slate-400 hover:text-slate-700 dark:hover:text-slate-300 hover:border-slate-300 dark:hover:border-slate-600'
          "
        >
          Convert
        </router-link>
        <router-link
          to="/compare"
          class="px-6 py-3 text-sm font-medium transition-colors border-b-2 -mb-px"
          :class="
            route.name === 'compare'
              ? 'border-indigo-600 text-indigo-600 dark:text-indigo-400'
              : 'border-transparent text-slate-500 dark:text-slate-400 hover:text-slate-700 dark:hover:text-slate-300 hover:border-slate-300 dark:hover:border-slate-600'
          "
        >
          Compare
        </router-link>
      </nav>

      <!-- Router View -->
      <router-view />
    </div>
  </div>
</template>

<style>
.font-tibetan {
  font-family: TibetanChogyalUnicode-170221, TibetanChogyalUnicode-ID,
    TibetanChogyalUnicode, TibetanMachineUnicode, sans-serif;
}
</style>
