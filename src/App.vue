<template>
  <v-app>
    <Layout />
  </v-app>
</template>

<script>
import Layout from "./components/Layout.vue";
export default {
  name: "App",
  components: {
    Layout,
  },
};
</script>
<style>
* {
  box-sizing: border-box;
}
body {
  font-family: Arial, Helvetica, sans-serif;
}
/* #icon {
  padding: 10px 10px 20px;
  margin: 1rem 2rem 3rem 2rem;
  width: 70px;
  height: 70px;
} */
/* .open {
  transform: translateY(300px);
} */
</style>
