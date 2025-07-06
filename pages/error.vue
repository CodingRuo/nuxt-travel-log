<script setup lang=ts>
const route = useRoute();
const error = route.query.error || "An unknown error occured";
</script>

<template>
  <div class="card container mt-4 min-h-screen mx-auto flex flex-col justify-center items-center gap-4">
    <div role="alert" class="alert alert-error min-w-1/2 text-center">
      <span>Oh no! {{ error }}</span>
    </div>
    <NuxtLink to="/" class="btn btn-primary">
      Home
      <Icon name="tabler:arrow-left" size="32" />
    </NuxtLink>
  </div>
</template>

<style scoped>
</style>
