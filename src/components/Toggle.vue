<template>
  <div class="toggle-wrapper">
    <label class="toggle">
      <input
        type="checkbox"
        :checked="mode === 'dark' ? 'checked' : false"
        @change="$emit('toggle')"
      />
      <span class="toggler round"></span>
    </label>
  </div>
</template>

<script>
export default {
  props: ["mode"],
};
</script>

<style scoped>
.toggle {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 35px;
}
.toggle input {
  opacity: 0;
  width: 0;
  height: 0;
}
.toggler {
  position: absolute;
  cursor: pointer;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background: rgba(11, 11, 39, 0.87);
  -webkit-transition: all 0.4s;
  transition: all 0.4s;
}

.toggler::before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background: #fff;
}
input:checked + .toggler {
  background: #116bb6;
}
input:focus + .toggler {
  box-shadow: 0 0 2px #116bb6;
}

input:checked + .toggler:before {
  transform: translateX(26px);
}

.toggler.round {
  border-radius: 34px;
}
.toggler.toggler.round::before {
  border-radius: 50%;
}
</style>