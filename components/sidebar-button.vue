<script lang="ts" setup>
const props = defineProps<{
  label: string;
  icon: string;
  href: string;
  showLabel: boolean;
}>();
const route = useRoute();
</script>

<template>
  <div class="tooltip-right" :data-tip="props.showLabel ? undefined : props.label" :class="{ tooltip: !props.showLabel }">
    <NuxtLink :to="props.href" :class="{ 'bg-base-300': route.path === props.href, 'justify-center': !props.showLabel, 'justify-start': props.showLabel }" class="flex gap-2 flex-nowrap btn p-2 hover:bg-base-300 hover:cursor-pointer">
      <Icon :name="props.icon" size="24" />
      <Transition name="grow">
        <span v-if="props.showLabel">
          {{ props.label }}
        </span>
      </Transition>
    </NuxtLink>
  </div>
</template>

<style scoped>
.grow-enter-active {
  animation: grow 0.2s;
}

.grow-enter-leave {
  animation: grow 0.2s reverse;
}

@keyframes grow {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}
</style>
