<script setup>

import Navbar from "@/components/Navbar.vue";
</script>

<template>

  <div class="flex flex-col">
    <Navbar></Navbar>

    <div class="w-screen flex-1">
      <RouterView></RouterView>
    </div>

  </div>
</template>

<style scoped>
</style>
