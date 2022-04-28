<template>
  <div class="app">
    <taskOne />
    <taskTwo />
    <taskThree />
  </div>
</template>

<script >
import taskOne from "./components/taskOne.vue";
import taskTwo from "./components/taskTwo.vue";
import taskThree from "./components/taskThree.vue";

export default {
  name: "App",
  components: {
    taskOne,
    taskTwo,
    taskThree,
  },
};
</script>

