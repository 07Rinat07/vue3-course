<template>

  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="fetchPosts">Получить посты</my-button>

    <my-button @click="showDialog"
    style="margin: 15px 0;"
    >
      Создать пользователя
    </my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form
          @create="createPost"
      />
    </my-dialog>

    <post-list
        :posts="posts"
        @remove="removePost"
    />
  </div>
</template>


<script>
import PostForm from "./components/PostForm.vue";
import PostList from "@/components/PostList.vue";
import MyDialog from "@/components/UI/MyDialog.vue";
import MyButton from "@/components/UI/MyButton.vue";
import axios from "axios";

export default {
  components: {
    MyButton,
    MyDialog,
    PostList, PostForm
  },

  data() {
    return {
      posts: [],
      dialogVisible: false,

    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchPosts() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
       this.posts = response.data;
      } catch (e) {
        alert('Error')
      }
    }
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