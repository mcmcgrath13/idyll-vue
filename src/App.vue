<template>
  <div class="container">
    <Idyll file="hello_world" />
  </div>
</template>

<script>
import Idyll from "./components/Idyll.vue";

export default {
  name: "App",
  components: {
    Idyll,
  },
};
</script>
