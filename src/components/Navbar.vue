<template>
  <div class="navbar">
    <div @click="$router.push('/')">Vue3</div>
    <div class="navbar__btns">
      <my-button @click="$router.push('/users')">Users</my-button>
      <my-button style="margin-left: 20px" @click="$router.push('/about')" >About Site</my-button>
    </div>
  </div>
</template>

<script>
import router from "@/router/router";

export default {
  methods: {
    router() {
      return router
    }
  }

}
</script>

<style scoped>
.navbar {
  height: 50px;
  background-color: lightgray;
  box-shadow: 2px 2px 4px rgb(128, 128, 128);
  display: flex;
  align-items: center;
  padding: 0 15px;
}
.navbar__btns {
  margin-left: auto;
}
</style>