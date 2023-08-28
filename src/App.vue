<template>

  <div class="app">
    <form>
      <h4>Создание поста</h4>
      <input
          v-bind:value="title"
          @input="title = $event.target.value"
          class="input"
          type="text"
          placeholder="Название">
      <input
          v-bind:value="body"
          @input="body = $event.target.value"
          class="input"
          type="text"
          placeholder="Описание"
      >
      <button class="btn" @click="createPost">Создать</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong>{{ post.title}}</div>
      <div><strong>Описание:</strong>{{ post.body}}</div>
    </div>
  </div>

</template>


<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'JS', body: 'Description 1'},
        {id: 2, title: 'PHP', body: 'Description 2'},
        {id: 3, title: 'Python', body: 'Description 3'},
        {id: 4, title: 'C++', body: 'Description  4'},
      ],
      title: '',
      body: ''
    }
  },
  methods: {
    createPost() {

    },
  }
}

</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin: 10px;
}

 form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

</style>