<template>
  <div v-if="todo.id">
    <Header />
    <div class="container">
      <h1>Edit</h1>
      <Form :info="todo" />
    </div>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Edit todo',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Edit todo',
      },
    ],
  },
  data() {
    return {
      todo: {},
    }
  },
  validate({ params }) {
    // Должен быть числом
    return /^\d+$/.test(params.id)
  },
  mounted() {
    const todos = JSON.parse(localStorage.getItem('todos'))
    this.todo = todos.find(
      (item) => parseInt(item.id) === parseInt(this.$route.params.id)
    )
  },
}
</script>
