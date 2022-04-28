<template>
  <h2>{{ textTask }}</h2>
  <div class="search-bar">
    <h3>{{ textSubject }}</h3>
    <input
      type="text"
      placeholder="Type name"
      @input="searchText = $event.target.value"
    />
    <p>Users: {{ users.length }} Filtered: {{ getFilteredUsers.length }}</p>
    <ul style="list-style: none">
      <li v-for="(user, index) in getFilteredUsers" :key="index">
        {{ user }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "taskTwo",
  data() {
    return {
      textTask: "Task Two",
      textSubject: "Search for users",
      searchText: "",
      users: ["John", "Bill", "Evgenij", "Maris", "Janis"],
    };
  },
  methods: {
    // getUsers(user) {
    //   return `${user.firstName}`;
    // },
  },
  computed: {
    getFilteredUsers() {
      return this.users.filter((user) =>
        user.toLowerCase().includes(this.searchText.toLowerCase())
      );
    },
  },
};
</script>

<style>
</style>