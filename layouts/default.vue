<script setup lang=ts>

</script>

<template>
  <div class="flex h-screen flex-col overflow-hidden">
    <AppNavBar />
    <main class="flex-1 overflow-hidden">
      <slot />
    </main>
  </div>
</template>
