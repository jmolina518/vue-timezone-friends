<template>
  <div>
    <p>Date : {{ getUsTimeZone }}</p>
    <p>Time : {{ getEsTimeZone }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newDate: new Date(),
      timer: null,
    };
  },
  props: {
    timezone: String,
  },
  computed: {
    getUsTimeZone() {
      return this.newDate.toLocaleDateString('en-US', {
        timeZone: this.timezone,
      });
    },
    getEsTimeZone() {
      return this.newDate.toLocaleTimeString('es-ES', {
        timeZone: this.timezone,
      });
    },
  },
  mounted() {
    this.timer = setInterval(() => (this.newDate = new Date()), 1000);
  },
  unmounted() {
    clearInterval(this.timer);
  },
};
</script>

<style></style>
