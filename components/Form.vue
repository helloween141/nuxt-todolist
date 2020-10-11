<template>
  <form>
    <div class="form-group">
      <label for="titleInput">Title</label>
      <input
        id="titleInput"
        v-model="title"
        type="text"
        class="form-control"
        aria-describedby="titleHelp"
      />
    </div>
    <div class="form-group">
      <label for="AnnotationInput">Annotation</label>
      <textarea
        id="AnnotationInput"
        v-model="annotation"
        class="form-control"
      ></textarea>
    </div>
    <button type="button" class="btn btn-primary" @click="create">
      Create
    </button>
  </form>
</template>
<style scoped>
form {
  margin-top: 30px;
}
</style>
<script>
export default {
  props: {
    info: {
      type: Object,
      default() {
        return {}
      },
    },
  },
  data() {
    return {
      title: this.info.title,
      annotation: this.info.annotation,
    }
  },
  methods: {
    create() {
      if (this.title.trim()) {
        const todos = JSON.parse(localStorage.getItem('todos')) || []
        const todo = {
          id: todos.length + 1,
          title: this.title,
          annotation: this.annotation,
          completed: false,
        }
        todos.push(todo)
        localStorage.setItem('todos', JSON.stringify(todos))
        if (this.info.id) {
          this.$toast.show('Todo was updated!').goAway(1500)
        } else {
          this.title = ''
          this.annotation = ''
          this.$toast.show('Todo was added!').goAway(1500)
        }
      }
    },
  },
}
</script>
