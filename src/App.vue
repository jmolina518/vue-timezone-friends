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
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid grey;
  padding: 30px;
  border-radius: 5px;
}
</style>
