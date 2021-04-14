<template>
  <header>
    <h1>{{ mode }} Mode</h1>
    <!-- toggle -->
    <toggle :mode="mode" @change="$emit('toggle')"></toggle>
    <nav>
      <div class="nav-link">Home</div>
      <div class="nav-link">About</div>
      <div class="nav-link">Portfolio</div>
      <div class="nav-link">Contact</div>
    </nav>
  </header>
</template>

<script>
import Toggle from "./Toggle.vue";
export default {
  props: ["mode"],
  components: {
    Toggle,
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 25px;
  height: 60px;
  background: #c3c3c3;
  transition: all 0.3s ease-in-out;
}
.dark header {
  background: rgba(11, 11, 39, 0.87);
}
header h1 {
  font-size: 32px;
  text-transform: uppercase;
  font-weight: 900;
}

header nav {
  display: flex;
  height: 60px;
}
header nav .nav-link {
  display: flex;
  align-items: center;
  padding: 0 15px;
}
header nav .nav-link:hover {
  background: #f3f3f3;
}
.dark header nav .nav-link:hover {
  background: rgba(22, 22, 97, 0.87);
}
</style>