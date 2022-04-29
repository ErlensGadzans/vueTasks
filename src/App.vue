<template>
  <div class="app">
    <!-- <taskOne />
    <taskTwo />
    <taskThree /> -->
    <taskFour />
  </div>
</template>

<script >
import taskOne from "./components/taskOne.vue";
import taskTwo from "./components/taskTwo.vue";
import taskThree from "./components/taskThree.vue";
import taskFour from "./components/taskFour.vue";

export default {
  name: "App",
  components: {
    taskOne,
    taskTwo,
    taskThree,
    taskFour,
  },
};
</script>

