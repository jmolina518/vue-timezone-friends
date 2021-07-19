<template>
  <input
    class="search"
    type="text"
    v-model="search"
    placeholder="Search Users..."
  />
  <div class="outer-container">
    <div class="container">
      <div class="card" v-for="user in filteredUsers" :key="user.id">
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
      search: '',
    };
  },
  computed: {
    filteredUsers() {
      return this.users.filter((user) => {
        return user.name.toLowerCase().match(this.search);
      });
    },
  },
};
</script>

<style scoped>
.outer-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 auto;
}
.container {
  display: grid;
  justify-content: center;
  width: 80vw;
  max-width: 2000px;
  margin: 0 auto;
  grid-template-columns: repeat(auto-fit, minmax(350px, max-content));
  row-gap: 20px;
  column-gap: 3rem;
}

.card {
  display: flex;
  text-align: left;
  -moz-column-gap: 1rem;
  column-gap: 1rem;
  align-items: center;
  justify-self: center;
  width: 36vw;
  background: #fff;
  box-shadow: 0 5px 15px rgb(0 0 0 / 40%);
  min-width: 300px;
  max-width: 350px;
  margin: 1.5rem 0.5rem;
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
.search {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  margin: 0 auto;
  border: none;
  width: 15%;
  line-height: 30px;
  margin-bottom: 15px 30px;
  border: 1px solid grey;
  border-radius: 7px;
  height: 50px;
  padding: 2px 23px 2px 30px;
  outline: 0;
  font-family: 'Poppins', sans-serif;
  font-size: 1rem;
  background-color: #f5f5f5;
}
</style>
