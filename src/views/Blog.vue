<template>
  <Layout>
    <h2 class="text-2xl font-semibold mb-4">Blog</h2>
    <div class="space-y-4">
      <div v-for="n in 3" :key="n" class="bg-white p-4 rounded shadow">
        <h3 class="text-lg font-semibold">Artikel {{ n }}</h3>
        <p class="text-gray-500 text-sm">12 Juni 2025</p>
        <p class="text-gray-600 mt-2">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      </div>
    </div>
  </Layout>
</template>

<script setup lang="ts">
import Layout from '../components/Layout.vue'
</script>