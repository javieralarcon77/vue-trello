<template>
  <section>
    <h3><span>Mis Paneles</span> ▸ {{ name }}</h3>
    <div class="input-container">
      <input
        type="text"
        placeholder="Añade una lista"
        v-model="listName"
        @keyup.enter="add()"
      >
    </div>
    <div class="container">
      <column
        v-for="(list, index) in boardList"
        :key="index"
        :listId="list.id"
        :name="list.name"
      ></column>
    </div>
  </section>
</template>

<script>
import Column from '@/components/Column'

export default {
  name: 'board-view',
  components: { Column },
  props: {
    id: String,
    name: String
  },
  data: function () {
    return {
      listName: '',
      boardList: [
        { id: 1, name: 'Todo' },
        { id: 2, name: 'Done' }
      ]
    }
  },
  methods: {
    add: function () {
      this.boardList.push({ name: this.listName })
      this.listName = ''
    }
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

  input{
    background-color: #546E7A;
    border: 0;
    border-radius: 5px;
    box-shadow: 0 0 0 0.5px rgba(49,49,93,.03),
      0 2px 5px 0 rgba(49,49,93,.1),
      0 1px 2px 0 rgba(0,0,0,.08);
    color: #607d8b;
    font-size: 1.2rem;
    margin: 0 1rem;
    outline: 0;
    padding: 1rem;
    transition: all 200ms ease;

    &:focus,
    &:active{
      background-color: #fafafa;
    }

    &::placeholder{
      color:white;
    }
  }
</style>
