<template>
  <div class="home">
    <h1>Welcome to the App!</h1>
    <template v-if="!this.$store.state.user">
      <div>
        To use the app, you'll need to
        <router-link to="authenticate">
          Login
        </router-link>
      </div>
    </template>
  </div>
</template>
