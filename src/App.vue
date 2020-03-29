<template>
  <v-app id="app" class="d-flex">
    <SignUp />
  </v-app>
</template>

<script>
import SignUp from "./components/SignUp";

export default {
  name: "App",
  components: {
    SignUp
  }
};
</script>

<style lang="sass">
$bg: #ffffff
*
  box-sizing: content-box

#app
  width: 100%
  height: 100%
  background-color: $bg
</style>
