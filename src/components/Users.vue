<template>
  <div class="container">
    <article class="person" v-for="user in users" :key="user.id">
      <a :href="user.twitter" target="_blank">
        <img :src="user.image" alt="profile pic" />
      </a>
      <div>
        <h4>{{ user.name }}</h4>
        <p>{{ user.timezone }}</p>
        <DateTime :timezone="user.timezone" class="date" />
      </div>
    </article>
  </div>
</template>

<script>
import usersData from '../json/users.json';
import DateTime from './DateTime';

export default {
  components: {
    DateTime,
  },
  data() {
    return {
      users: usersData,
    };
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.person {
  display: grid;
  grid-template-columns: auto 1fr;
  column-gap: 0.75rem;
  align-items: center;
  width: 90vw;
  background: #fff;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
  max-width: 300px;
  margin: 30px auto;
  margin-bottom: 1.5rem;
  overflow: auto;
  min-height: 100px;
  border: 1px solid grey;
  padding: 30px;
  border-radius: 5px;
}
.person img {
  width: 75px;
  height: 75px;
  object-fit: cover;
  border-radius: 50%;
  /* box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1); */
}
.person h4 {
  margin-bottom: 0.35rem;
}
.person p {
  margin-bottom: 0;
}
</style>
