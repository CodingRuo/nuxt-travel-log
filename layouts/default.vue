<script setup lang=ts>
const authStore = useAuthStore();
await authStore.init();
</script>

<template>
  <div class="flex h-screen flex-col overflow-hidden">
    <AppNavBar />
    <main class="flex-1 overflow-hidden">
      <slot />
    </main>
  </div>
</template>
