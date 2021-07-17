<template>
  <div class="outer-container">
    <div class="container">
      <div class="card" v-for="user in users" :key="user.id">
        <a :href="user.twitter" target="_blank" class="img-link">
          <img :src="user.image" alt="profile pic" />
        </a>
        <div class="info">
          <h4>{{ user.name }}</h4>
          <p>{{ user.timezone }}</p>
          <DateTime :timezone="user.timezone" class="date" />
        </div>
      </div>
    </div>
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
.outer-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
}
.container {
  display: flex;
  flex-direction: row;
  /* justify-content: center; */
  flex-wrap: wrap;
  width: 80vw;
  max-width: 2000px;
  margin: 0 auto;
}

.card {
  display: flex;
  text-align: left;
  column-gap: 1rem;
  align-items: center;
  justify-content: space-around;
  width: 90vw;
  background: #fff;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
  max-width: 350px;
  margin: 1.5rem 1.5rem;
  min-height: 100px;
  border: 1px solid grey;
  padding: 30px 15px;
  border-radius: 7px;
}

.card img {
  width: 90px;
  height: 90px;
  object-fit: cover;
  border-radius: 50%;
  align-self: center;
  justify-self: center;
}
.card h4 {
  margin-bottom: 0.35rem;
}
.card p {
  margin-bottom: 0;
}
.info p,
.date {
  color: grey;
}
.img-link {
  margin: 0;
  padding: 0;
  max-height: 90px;
}
</style>
