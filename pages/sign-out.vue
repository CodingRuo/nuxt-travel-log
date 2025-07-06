<script setup lang=ts>
const authStore = useAuthStore();

onMounted(() => {
  authStore.signOut();
});
</script>

<template>
  <div class="card container mt-4 min-h-screen mx-auto flex flex-col justify-center items-center gap-4">
    <span class="loading loading-spinner loading-xl" />
  </div>
</template>

<style scoped>
</style>
