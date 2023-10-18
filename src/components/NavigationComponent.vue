<template>
  <nav>
    <button @click="changeTab('home')" :class="{ active: currentTab === 'home' }">HOME</button>
    <button @click="changeTab('aboutMe')" :class="{ active: currentTab === 'aboutMe' }">ABOUT ME</button>
  </nav>
</template>

<script>
export default {
  props: {
    currentTab: String,
  },
  methods: {
    changeTab(tab) {
      this.$emit('changeTab', tab);
    },
  },
};
</script>

<style scoped>
nav {
  margin: 20px;
  display: flex;
  flex-direction: column;
}

button {
  color: white;
  text-align: left;
  font-weight: bold;
  padding: 10px 20px;
  width: 300px;
  font-size: 20px;
  background: none;
  border: none;
  cursor: pointer;
  clip-path: polygon(0 0, 100% 0, 90% 100%, 0 100%);
}

.active {
  background-color: rgb(107, 0, 207);
}
</style>