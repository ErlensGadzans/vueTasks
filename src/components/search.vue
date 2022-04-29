<template>
  <input type="text" class="search" v-model="searchText" />
  <button type="button" @click="$emit('search', searchText)">Search</button>
</template>

<script>
export default {
  name: "search",

  data() {
    return {
      searchText: "",
    };
  },
};
</script>

<style>
input {
  height: 25px;
  margin-left: 40px;
}
</style>