<template>
  <div class="container">
    <div v-if="todos.length > 0" class="row">
      <div v-for="todo in todos" :key="todo.id" class="col-sm-6">
        <div class="card">
          <div class="card-header">
            <h5 class="card-title">{{ todo.title }}</h5>
            <button
              type="button"
              class="btn btn-outline-primary remove-btn"
              @click="remove(todo.id)"
            >
              <svg
                width="1em"
                height="1em"
                viewBox="0 0 16 16"
                class="bi bi-trash-fill"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M2.5 1a1 1 0 0 0-1 1v1a1 1 0 0 0 1 1H3v9a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V4h.5a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1H10a1 1 0 0 0-1-1H7a1 1 0 0 0-1 1H2.5zm3 4a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7a.5.5 0 0 1 .5-.5zM8 5a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-1 0v-7A.5.5 0 0 1 8 5zm3 .5a.5.5 0 0 0-1 0v7a.5.5 0 0 0 1 0v-7z"
                ></path>
              </svg>
            </button>
          </div>
          <div class="card-body">
            <p class="card-text">
              {{ todo.annotation }}
            </p>
            <NuxtLink :to="`/todo/${todo.id}`" class="nav-link">Edit</NuxtLink>
          </div>
        </div>
      </div>
    </div>
    <div v-else class="row">
      <span> You have no todos yet :( </span>
    </div>
  </div>
</template>
<style scoped>
.card {
  margin-bottom: 20px;
}
.card .card-header .card-title {
  display: inline;
}
.card .card-header .remove-btn {
  float: right;
}
.nav-link {
  padding: 0;
}
</style>
<script>
export default {
  data() {
    return {
      todos: [],
    }
  },
  mounted() {
    this.todos = JSON.parse(localStorage.getItem('todos'))
  },
  methods: {
    remove(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
      localStorage.setItem('todos', JSON.stringify(this.todos))
    },
  },
}
</script>
