<template>
  <UserProfile />
</template>

<script>
import UserProfile from "./components/UserProfile.vue";
export default {
  components: { UserProfile },
  name: "App",
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,300&display=swap");
#app {
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-direction: row;
  align-items: center;
}
</style>
