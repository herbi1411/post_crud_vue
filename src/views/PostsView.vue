<template>
  <div class="container d-flex flex-column">
    <div v-for="post in posts" :key="post.id">
        <PostElement :post="post"/>
    </div>
  </div>
</template>

<script>
import PostElement from "@/components/PostElement.vue"
import axios from "axios"
export default {
  name: 'PostsView',
  components: {
    PostElement,
  },
  data: function (){
    return {
        posts: []
    }
  },
  created: function(){

  },
  mounted: function(){
    console.log("what the")
    this.getPosts()
  },
  methods: {
    getPosts: function() {
        axios.get("http://127.0.0.1:8080/posts")
        .then((response) => {
            this.posts = response.data.posts
        })
        .catch((error) => {
            console.log(error)
        })
    }
  },
}
</script>
