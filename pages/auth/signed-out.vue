<template>
  <p>
    <a v-if="$auth.loggedIn" @click="$auth.logout()">Press here to sign off</a>
  </p>
</template>

