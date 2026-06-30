<template>
  <Layout>
    <h2 class="text-2xl font-semibold mb-4">Dashboard</h2>
    <div class="grid grid-cols-3 gap-4">
      <div class="bg-blue-100 p-4 rounded shadow">
        <p class="text-gray-600">Total User</p>
        <p class="text-3xl font-bold">120</p>
      </div>
      <div class="bg-green-100 p-4 rounded shadow">
        <p class="text-gray-600">Total Post</p>
        <p class="text-3xl font-bold">45</p>
      </div>
      <div class="bg-yellow-100 p-4 rounded shadow">
        <p class="text-gray-600">Total View</p>
        <p class="text-3xl font-bold">3.2k</p>
      </div>
    </div>
  </Layout>
</template>

<script setup lang="ts">
import Layout from '../components/Layout.vue'
</script>