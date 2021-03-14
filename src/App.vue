<template>
  <div>
    <h1>Vue Tutorial</h1>
    <input type="text" v-model="message">
    <br>
    {{ message }}

    <ul>
      <li v-for="todo in todos" :key="todo.id" class="task-card">
        {{ todo.text }}
      </li>
    </ul>

  </div>
</template>

<script>

export default {
  name: 'App',
  data: function () {
    return {
      message: 'ハロー',
      todos: [
        { id: 0 , text: 'Rails も勉強しないと'},
        { id: 1 , text: '自動整形ツールを設定してみたい'},
        { id: 2 , text: 'Vue は今週中まで'},
      ],
    }
  },
};
</script>

<style>
.task-card {
 border: solid 1px;
 margin: 5px;
 padding: 2px;
 width: 250px;
}
</style>
