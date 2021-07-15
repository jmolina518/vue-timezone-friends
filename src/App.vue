<template>
  <Header />
  <div class="container">
    <Users />
  </div>
  <Footer />
</template>

<script>
import Header from './components/Header';
import Users from './components/Users';
import Footer from './components/Footer';

export default {
  name: 'App',
  components: {
    Header,
    Users,
    Footer,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
  background: #35495e;
}
</style>
