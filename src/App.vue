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
body {
  background: #35495e;
}

.container {
  width: 90vw;
  max-width: 450px;
  background: #fff;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
  align-items: center;
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid grey;
  padding: 30px;
  border-radius: 5px;
}
</style>
