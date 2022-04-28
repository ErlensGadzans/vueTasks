<template>
  <div class="root">{{ text }}</div>
  <div class="input-container">
    <button @click="decreaseNumber">-</button>
    <input type="number" :value="number" :min="minNumber" :max="maxNumber" />
    <button @click="inceaseNumber">+</button>
  </div>
</template>

<script>
export default {
  name: "MyComponent",
  data() {
    return {
      text: "Choose amount of products",
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
