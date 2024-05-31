<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HeaderNav from '@/components/HeaderNav.vue';
</script>

<template>
  <div class="container mt-5">
    <div>
      <HeaderNav />
    </div>
    <div class="view-page mt-3">
      <RouterView />
    </div>

  </div>
</template>