<template>
  <div>
    <super-secret-div v-if="$auth.loggedIn"/>
    <div class="content">
      <h1>Hei, {{ $auth.loggedIn ? $auth.user.email : 'friend' }}!</h1>
      <p v-if="$auth.loggedIn">Now try going to our
        <nuxt-link to="/secret" class="link">super secret page</nuxt-link>!
      </p>
      <p v-else>
        So, maybe you want to
        <a @click="$auth.login()" class="link">sign in</a> and see what happens?
      </p>
    </div>
  </div>
</template>

<script>
import SuperSecretDiv from "~/components/SuperSecretDiv";

export default {
  components: {
    SuperSecretDiv
  }
};
</script>

<style scoped>
.content {
  max-width: 750px;
  margin: 0 auto;
  text-align: center;
}
</style>
