<template>
  <aside class="bg-gray-100 w-60 min-h-screen p-6 shadow">
    <nav class="space-y-4">
      <RouterLink to="/" class="block hover:text-blue-600">🏠 Home</RouterLink>
      <RouterLink to="/dashboard" class="block hover:text-blue-600">📊 Dashboard</RouterLink>
      <RouterLink to="/profile" class="block hover:text-blue-600">👤 Profile</RouterLink>
      <RouterLink to="/gallery" class="block hover:text-blue-600">🖼️ Gallery</RouterLink>
      <RouterLink to="/blog" class="block hover:text-blue-600">📝 Blog</RouterLink>
      <RouterLink to="/settings" class="block hover:text-blue-600">⚙️ Settings</RouterLink>
      <RouterLink to="/about" class="block hover:text-blue-600">ℹ️ About</RouterLink>
      <RouterLink to="/contact" class="block hover:text-blue-600">📬 Contact</RouterLink>
    </nav>
  </aside>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>