<template>

  <div class="app">
    <post-form/>
    <post-list/>
  </div>

</template>


<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
  components: {
    PostList, PostForm
  },

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
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';
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

</style>