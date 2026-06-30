<template>
  <Layout>
    <h2 class="text-2xl font-semibold mb-4">Settings</h2>
    <div class="bg-white p-6 rounded shadow max-w-md space-y-4">
      <div class="flex justify-between items-center">
        <p class="text-gray-700">Dark Mode</p>
        <input type="checkbox" class="w-5 h-5" />
      </div>
      <div class="flex justify-between items-center">
        <p class="text-gray-700">Notifikasi</p>
        <input type="checkbox" class="w-5 h-5" />
      </div>
      <div class="flex justify-between items-center">
        <p class="text-gray-700">Bahasa</p>
        <select class="border rounded p-1 text-gray-600">
          <option>Indonesia</option>
          <option>English</option>
        </select>
      </div>
    </div>
  </Layout>
</template>

<script setup lang="ts">
import Layout from '../components/Layout.vue'
</script>