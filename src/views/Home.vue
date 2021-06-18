<template>
  <div>
    <h3>Mis Paneles</h3>
    <div class="input-container">
      <input
        type="text"
        placeholder="Añade un nuevo panel"
        v-model="boardName"
        @keyup.enter="add()"
      >
    </div>
    <div class="boards-collection">
      <board-card
        v-for="(board, index) in boards"
        :key="index"
        :name="board.name"
        :id="board.id"
      ></board-card>
    </div>
  </div>
</template>

<script>
import BoardCard from '@/components/BoardCard'

export default {
  name: 'home-view',
  components: { BoardCard },
  data: function () {
    return {
      boardName: '',
      boards: [
        {id: 1, name: 'Tareas'},
        {id: 2, name: 'Lista de la compra'}
      ]
    }
  },
  methods: {
    add: function () {
      this.boards.push({ name: this.boardName })
      this.boardName = ''
    }
  }
}
</script>

<style lang="scss" scoped>
  h3{
    text-align: left;
    margin: 1.5rem;
  }
  .boards-collection{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    padding-top: 1rem;
  }
  input{
    box-sizing: border-box;
    background-color: #546E7A;
    border: 2px solid #546E7A;
    border-radius: 3px;
    font-size: 1.1rem;
    outline: 0;
    padding: 0.5rem;
    transition: all 200ms ease;

    &:focus,
    &:active{
      background-color: white;
      color: #546E7A;
    }

    &::placeholder{
      color:white;
    }
  }
</style>
