<template>


  <div>
    <!-- Override Layout -->
    <!-- <NuxtLayout :name="layout">
       -->
    <NuxtLayout>
      <v-app>
        <NuxtPage />
      </v-app>
    </NuxtLayout>
  </div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.2s;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: grayscale(1);
}
</style>

<!-- Override Layout -->
<!-- <script setup>
const layout = 'another';
</script> -->