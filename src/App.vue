<template>
  <div>
    <h1>Vue Tutorial</h1>
    <input type="text" v-model="message">
    <button :disabled="isDisabled" @click="addTodo()">追加</button>
    <br>
    {{ message }}

    <ul>
      <TaskCard v-for="todo in todos" :key="todo.id" :text="todo.text" />
    </ul>

  </div>
</template>

<script>
import TaskCard from "@/components/TaskCard.vue";

export default {
  name: 'App',
  components: {
    TaskCard
  },
  data: function () {
    return {
      message: '',
      todos: [
        { id: 0 , text: 'Rails も勉強しないと'},
        { id: 1 , text: '自動整形ツールを設定してみたい'},
        { id: 2 , text: 'Vue は今週中まで'},
      ],
    }
  },
  computed: {
    isDisabled() {
      return this.message.length === 0;
    }
  },
  methods: {
    addTodo: function () {
      const newTodo = {
        id: this.todos.length + 1,
        text: this.message
      };
      this.todos.push(newTodo);
      this.message = "";
    }
  }
};
</script>

<style>

</style>
