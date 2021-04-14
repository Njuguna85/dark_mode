<template>
  <div class="app" :class="mode == 'dark' ? 'dark' : 'light'">
    <the-header :mode="mode" @toggle="toggle"></the-header>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
export default {
  data() {
    return {
      mode: "light",
    };
  },
  components: {
    TheHeader,
  },
  methods: {
    toggle() {
      if (this.mode === "dark") {
        this.mode = "light";
      } else {
        this.mode = "dark";
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}

.app {
  width: 100vw;
  min-height: 100vh;
  background-color: #f3f3f3;
  color: rgba(11, 11, 39, 0.87);
  transition: all 0.3s ease-in-out;
}

.dark {
  background-color: rgba(11, 11, 39, 0.87);
  color: #f3f3f3;
}
</style>
