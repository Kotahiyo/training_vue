<template>
  <li class="task-card">
    <span>{{ text }}</span>
    <button @click="remove">削除</button>
  </li>
</template>

<script>
export default {
  name: "TaskCard",
  props: {
    text: {
      type: String,
      default: ""
    },
    id: {
      type: Number,
      required: true
    }
  },
   methods: {
    remove() {
       this.$emit("remove-task", this.id)
    }
  }
}
</script>

<style>
.task-card {
 border: solid 1px;
 margin: 5px;
 padding: 2px;
 width: 250px;
}

</style>
