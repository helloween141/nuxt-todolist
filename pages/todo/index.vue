<template>
  <div>
    <Header />
    <div class="container">
      <h1>Create</h1>
      <Form />
    </div>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Create todo',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Create todo',
      },
    ],
  },
}
</script>
