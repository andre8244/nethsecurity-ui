<script setup lang="ts">
import { useLoginUserStore } from '@/stores/loginUser'

// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome' ////
// import { faUserSecret } from '@nethesis/nethesis-solid-svg-icons' ////
// library.add(faUserSecret)

const loginUserStore = useLoginUserStore()

function login() {
  console.log('login') ////

  loginUserStore.setLoggedIn(true)
}
</script>

<template>
  <div>
    <h1>Login</h1>
    <!-- <font-awesome-icon icon="fa-solid fa-user-secret" size="2xs" />
    <font-awesome-icon icon="fa-solid fa-user-secret" size="2m" />
    <font-awesome-icon :icon="['fas', 'user-secret']" size="2xl" />
    <font-awesome-icon :icon="['fas', 'user-secret']" size="3x" />
    <font-awesome-icon :icon="['fas', 'user-secret']" size="5x" />
    <font-awesome-icon :icon="['fas', 'user-secret']" size="10x" /> -->
  </div>
  <button @click="login">Login</button>
</template>
