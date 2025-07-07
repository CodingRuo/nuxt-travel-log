<script setup lang=ts>
const links = {
  location: {
    label: "Locations",
    icon: "tabler:map",
    href: "/dashboard",
  },
  addLocation: {
    label: "Add Location",
    icon: "tabler:plus",
    href: "/dashboard/add",
  },
  logout: {
    label: "Logout",
    icon: "tabler:logout-2",
    href: "/sign-out",
  },
};
const isSidebarOpen = ref(true);

onMounted(() => {
  isSidebarOpen.value = localStorage.getItem("isSidebarOpen") === "true";
});

function toggleSidebar() {
  isSidebarOpen.value = !isSidebarOpen.value;
  localStorage.setItem("isSidebarOpen", isSidebarOpen.value.toString());
}
</script>

<template>
  <div class="flex-1 flex">
    <div class="bg-base-200 transition-all duration-300" :class="{ 'w-64': isSidebarOpen, 'w-16': !isSidebarOpen }">
      <div class="flex cursor-pointer hover:bg-base-300 py-2" :class="{ 'justify-center': !isSidebarOpen, 'justify-end': isSidebarOpen }" @click="toggleSidebar">
        <Icon v-if="!isSidebarOpen" name="tabler:chevron-right" size="32" />
        <Icon v-else name="tabler:chevron-left" size="32" />
      </div>
      <div class="flex flex-col">
        <template v-for="[key, { label, icon, href }] in Object.entries(links)" :key="key">
          <SidebarButton :label="label" :icon="icon" :href="href" :show-label="isSidebarOpen" />
          <div v-if="key === 'addLocation'" class="divider" />
        </template>
      </div>
    </div>
    <div class="flex-1 " />
  </div>
</template>
