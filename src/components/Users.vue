<template>
  <article class="person" v-for="user in users" :key="user.id">
    <img :src="user.image" alt="" />
    <div>
      <h4>{{ user.name }}</h4>
      <p>{{ user.timezone }}</p>
    </div>
  </article>
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
.person {
  display: grid;
  grid-template-columns: auto 1fr;
  column-gap: 0.75rem;
  margin-bottom: 1.5rem;
  align-items: center;
}
.person img {
  width: 75px;
  height: 75px;
  object-fit: cover;
  border-radius: 50%;
  box-shadow: var(--light-shadow);
}
.person h4 {
  margin-bottom: 0.35rem;
}
.person p {
  margin-bottom: 0;
}
</style>
