<template>
  <Layout>
    <h2 class="text-2xl font-semibold mb-4">Profile</h2>
    <div class="bg-white p-6 rounded shadow max-w-md">
      <div class="flex items-center gap-4 mb-4">
        <div class="bg-blue-500 text-white rounded-full w-16 h-16 flex items-center justify-center text-2xl font-bold">
          A
        </div>
        <div>
          <p class="text-xl font-semibold">Nama Kamu</p>
          <p class="text-gray-500">namakamu@email.com</p>
        </div>
      </div>
      <p class="text-gray-600">Mahasiswa Teknik Informatika</p>
    </div>
  </Layout>
</template>

<script setup lang="ts">
import Layout from '../components/Layout.vue'
</script>