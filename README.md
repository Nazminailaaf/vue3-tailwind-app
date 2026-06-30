# Vue 3 + Tailwind — Layouting & API Integration

Aplikasi Vue 3 (Vite + TypeScript + TailwindCSS) dengan:

- **Layouting**: `Header`, `Sidebar`, `Layout` (wrapper) dipakai di semua halaman lewat Vue Router (`Home`, `About`, `Contact`, `Dashboard`, `Profile`, `Gallery`, `Blog`, `Settings`).
- **Integrasi API**: halaman **Gallery** mengambil data user dari [reqres.in](https://reqres.in) (`GET /api/users?page=N`) memakai `fetch`, lengkap dengan state `loading`, `error`, dan pagination (tombol Sebelumnya/Berikutnya).

## Menjalankan secara lokal

```bash
npm install
npm run dev
```

Build production:

```bash
npm run build
```

## Struktur

```
src/
  components/   Header.vue, Sidebar.vue, Layout.vue
  views/        Home, About, Contact, Dashboard, Profile, Gallery (API), Blog, Settings
  router/       index.ts
```
