<template>
  <Layout>
    <div class="flex items-center justify-between mb-4">
      <h2 class="text-2xl font-semibold">Gallery — User Directory</h2>
      <span class="text-sm text-gray-500">Sumber data: reqres.in API</span>
    </div>

    <div v-if="loading" class="text-gray-500 py-10 text-center">
      Memuat data dari API...
    </div>

    <div v-else-if="error" class="bg-red-100 text-red-700 p-4 rounded shadow">
      Gagal memuat data: {{ error }}
      <button @click="fetchUsers" class="ml-2 underline text-red-800">Coba lagi</button>
    </div>

    <div v-else>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
        <div
          v-for="user in users"
          :key="user.id"
          class="bg-white rounded shadow hover:shadow-lg transition p-4 flex flex-col items-center text-center"
        >
          <img
            :src="user.avatar"
            :alt="`${user.first_name} ${user.last_name}`"
            class="w-20 h-20 rounded-full mb-3 object-cover"
          />
          <p class="font-semibold">{{ user.first_name }} {{ user.last_name }}</p>
          <p class="text-gray-500 text-sm">{{ user.email }}</p>
        </div>
      </div>

      <div class="flex items-center justify-center gap-4 mt-6">
        <button
          class="px-4 py-2 bg-blue-600 text-white rounded shadow disabled:opacity-40"
          :disabled="page <= 1"
          @click="changePage(page - 1)"
        >
          ← Sebelumnya
        </button>
        <span class="text-gray-600">Halaman {{ page }} dari {{ totalPages }}</span>
        <button
          class="px-4 py-2 bg-blue-600 text-white rounded shadow disabled:opacity-40"
          :disabled="page >= totalPages"
          @click="changePage(page + 1)"
        >
          Berikutnya →
        </button>
      </div>
    </div>
  </Layout>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'
import Layout from '../components/Layout.vue'

interface ApiUser {
  id: number
  email: string
  first_name: string
  last_name: string
  avatar: string
}

const users = ref<ApiUser[]>([])
const loading = ref(true)
const error = ref<string | null>(null)
const page = ref(1)
const totalPages = ref(1)

async function fetchUsers() {
  loading.value = true
  error.value = null
  try {
    const res = await fetch(`https://reqres.in/api/users?page=${page.value}`, {
      headers: { 'x-api-key': 'reqres-free-v1' },
    })
    if (!res.ok) throw new Error(`HTTP ${res.status}`)
    const data = await res.json()
    users.value = data.data
    totalPages.value = data.total_pages
  } catch (e) {
    error.value = e instanceof Error ? e.message : 'Unknown error'
  } finally {
    loading.value = false
  }
}

function changePage(newPage: number) {
  if (newPage < 1 || newPage > totalPages.value) return
  page.value = newPage
  fetchUsers()
}

onMounted(fetchUsers)
</script>
