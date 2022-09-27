<template>
  <main>
    <h3 class="text-center pt-2">Post</h3>
    <div class="container">
      <div class="row">
         <PostCardComponent v-for="post in posts" :key="post.id" :post='post' />
      </div>
    </div>
  </main>
</template>

<script>
import PostCardComponent from './PostCard.vue';
import axios from 'axios';
export default {
     components: {
        PostCardComponent
     },
     data: function(){
        return{
            posts: []
        }
     },
     methods: {
        getPosts(){
            axios.get('/api/posts').then((response)=>{
                console.log(response.data.results);
                this.posts = response.data.results;
            })
        }
     },
     created(){
        this.getPosts();
     }
}
</script>

<style>

</style>