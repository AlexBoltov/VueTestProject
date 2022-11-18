<template>
  <div>
    <form @submit.prevent>
      <h4>Оставь свой отзыв</h4>
      <input 
        v-model="post.title"
        class="input" 
        type="text" 
        placeholder="Заголовок"
      >
      <input 
        v-model="post.body"
        class="input" 
        type="text" 
        placeholder="Содержание"
      >
      <button class="btn" @click="createPost">Опубликовать</button>
    </form>
  </div>
</template>


<script>
export default {
  name: 'PostForm',
  props: {
    msg: String
  },

  data() {
    return{
      post: {
        title: '',
        body: ''
      }
    }
  },

  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.post.title,
        body: this.post.body,
      }
      this.$emit('newPost', newPost),
      this.post.title='',
      this.post.body=''
    },
  },
}
</script>


<style scoped>
form {
  margin: 20px 0px;
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
}
</style>
