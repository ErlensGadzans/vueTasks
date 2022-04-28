<template>
  <div class="app">
    <taskOne />
    <taskTwo />
  </div>
</template>

<script >
import taskOne from "./components/taskOne.vue";
import taskTwo from "./components/taskTwo.vue";

export default {
  name: "App",
  components: {
    taskOne,
    taskTwo,
  },
};
</script>

