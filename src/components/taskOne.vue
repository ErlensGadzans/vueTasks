<template>
  <h2>{{ textTask }}</h2>
  <div class="root">{{ text }}</div>
  <div class="input-container">
    <button @click="decreaseNumber">-</button>
    <input type="number" :value="number" :min="minNumber" :max="maxNumber" />
    <button @click="inceaseNumber">+</button>
  </div>
</template>

<script>
export default {
  name: "taskOne",
  data() {
    return {
      textTask: "Task 1",
      text: "Choose amount of products (Maximum:10)",
      minNumber: 1,
      maxNumber: 10,
      number: 1,
    };
  },
  methods: {
    inceaseNumber() {
      if (this.number < this.maxNumber) {
        this.number++;
      }
    },
    decreaseNumber() {
      if (this.number > this.minNumber) {
        this.number--;
      }
    },
  },
};
</script>
