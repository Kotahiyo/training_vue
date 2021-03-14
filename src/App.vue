<template>
  <div>
    <h1>Vue Tutorial</h1>
    <input type="text" @input="onInput" />
    <!-- <input type="text" v-model="message"> -->
    <br>
    {{ message }}
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function () {
    return {
      message: 'ハロー'
    }
  },
  methods: {
    onInput: function (event) {
      const text = event.target.value;
      this.message = text;
    },
  }
};
</script>

<style>

</style>
