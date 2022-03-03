<template>
  <li>
    <label>
      <input
        type="checkbox"
        :checked="todo.done"
        @change="updateCheck(todo.id)"
      />
      <span>{{todo.title}}</span>
    </label>
    <button
      class="btn btn-danger"
      @click='handleTodo(todo.id)'
    >删除</button>
  </li>

</template>

<script>
export default {
  name: 'MyItem',
  props: ['todo', 'checkTodo', 'deleteTodo'],
  methods: {
    updateCheck(id) {
      this.checkTodo(id)
    },
    handleTodo(id) {
      if (confirm('确定要删除吗')) {
        this.deleteTodo(id)
      }
    }
  }
}
</script>

<style>
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li .btn {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
li:hover {
  background-color: #ddd;
}
li:hover .btn {
  display: block;
}
</style>