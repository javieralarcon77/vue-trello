<template>
  <footer>
    <span>Hecho con amor y <a href="//vuejs.org">vue.js</a></span>
  </footer>
</template>

<script>
export default {
  name: 'app-footer'
}
</script>

<style lang="scss" scoped>
footer {
  box-sizing: border-box;
  background-color: #cfd8dc;
  bottom: 0;
  left: 0;
  padding: 1rem;
  position: fixed;
  width: 100%;
  a {
    text-decoration: none;
    color: #546e74;
  }
}
</style>
