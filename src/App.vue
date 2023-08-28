<template>

  <div>
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
      ]
    }
  },
  methods: {

  }
}

</script>


<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin: 10px;
}

</style>