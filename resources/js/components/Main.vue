<template>
  <main>
    <h3 class="text-center pt-2">Post</h3>
    <PostCardComponent />
  </main>
</template>

<script>
import PostCardComponent from './PostCard.vue';
import axios from 'axios';
export default {
     components: {
        PostCardComponent
     },
     methods: {
        getPosts(){
            axios.get('/api/posts').then((response)=>{
                console.log(response.data.results);
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