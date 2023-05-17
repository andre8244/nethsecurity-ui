<script setup lang="ts">
import Shell from './components/Shell.vue' ////
import LoginView from './views/LoginView.vue' ////
import { useLoginUserStore } from '@/stores/loginUser'

const loginUserStore = useLoginUserStore()
</script>

<template>
  <div>NethSecurity</div>

  <template v-if="loginUserStore.isLoggedIn">
    <Shell />
  </template>
  <template v-else>
    <LoginView />
  </template>
</template>

<style scoped></style>
