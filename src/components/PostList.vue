<template>
    <div>
  
      <div class="post" v-for="post in posts" :key="post.id">
        <div><strong>{{post.title}}</strong></div>
        <div>{{post.body}}</div>
      </div>
    </div>
</template>


<script>
export default {
    name: 'PostList',
    props: {
        posts: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            
        }
    }
}
</script>


<style scoped>
.post {
  margin: 10px 0px;
  padding: 15px;
  border: 2px solid teal;
}
</style>