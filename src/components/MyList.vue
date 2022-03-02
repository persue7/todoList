<template>
  <ul class="todo-main">
    <MyItem
      v-for="todoObj in todoList"
      :key="todoObj.id"
      :todo='todoObj'
    ></MyItem>
  </ul>
</template>

<script>
import MyItem from './MyItem'

export default {
  name: 'MyList',
  components: {
    MyItem
  },

  data() {
    return {
      todoList: [
        { id: '001', title: '吃饭', done: true },
        { id: '002', title: '睡觉', done: false },
        { id: '003', title: '打豆豆', done: true }
      ]
    }
  },
}
</script>

<style>
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>