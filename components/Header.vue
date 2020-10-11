<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <NuxtLink to="/" class="navbar-brand">Todolist</NuxtLink>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div id="navbarSupportedContent" class="collapse navbar-collapse">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <NuxtLink to="/" class="nav-link">Dashboard</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/todo" class="nav-link">Create</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/about" class="nav-link">About</NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>
<style scoped>
.navbar {
  margin-bottom: 30px;
}
</style>
