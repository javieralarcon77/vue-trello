<template>
  <section>
    <h3><span>Mis Paneles</span> ▸ {{ name }}</h3>

  </section>
</template>

<script>
export default {
  name: 'board-view',
  components: {},
  props: {
    id: String,
    name: String
  }
}
</script>

<style lang="scss" scoped>
  section{
    text-align: left;
  }

  h3{
    color: #37474f;
    text-align: left;
    margin: 1.5rem;

    span{
      color: #546e7a;
    }
  }
</style>
