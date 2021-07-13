<template>
  <ul>
    <li v-for="user in users" :key="user.id">
      {{ user.name }}
    </li>
  </ul>
</template>

<script>
import usersData from '../json/users.json';
export default {
  data() {
    return {
      users: usersData,
    };
  },
};
</script>

<style scoped>
div {
  margin-top: 30px;
  text-align: center;
}
</style>
