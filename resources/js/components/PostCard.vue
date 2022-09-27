<template>
  <div class="col-4">
       <div class="pt-5">
          <h5>{{post.title}}</h5>
          <img :src="post.post_image" :alt="post.title" class="w-50 pt-2">
          <p class="pt-2">{{post.post_content.substring(0, 150)}}...altro</p>
       </div>
  </div>
</template>

<script>
export default {
   props: ['post']
}
</script>

<style>

</style>