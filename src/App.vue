<template>
  <div class="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Hello to Your Vue.js App</h1>
  
    <PostForm @newPost="createPost"/>
    <PostList v-bind:posts="posts"/>

    <div >Количество просмотров {{views}}</div>
    <div>Количество лайков {{likes}}</div>
    <div>
      <button @click="addLike">Like</button>
    </div>
  </div> 
</template>

<script>
import PostForm from '@/components/PostForm.vue'
import PostList from '@/components/PostList.vue'

export default {
  name: 'App',
  components: {
    PostForm,
    PostList
  },

  methods: {
    addLike() {
      this.likes += 1;
    },
    createPost(post) {
      this.posts.push(post)
    }
  },

  data() {
      return {
        likes: 73,
        views: 1378,
        posts: [
        {id: 1, title: 'Заголовок', body: 'Just opisanie'},
        {id: 2, title: 'Заголовок 2', body: 'Not just opisanie'},
        {id: 3, title: 'Заголовок 3', body: 'I dont know what i am opisanie'},
        ],
      }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  margin: 0;
  padding: 0px;
  box-sizing: border-box;
}
.app {
  padding: 15px;
}
</style>
