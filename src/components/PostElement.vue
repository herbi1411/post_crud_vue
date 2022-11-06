<template>
  <v-card>
    <p>{{post.title}}</p>
    <p>{{post.content}}</p>
  </v-card>
</template>

<script>
export default {
    name: "PostElement",
    props: {
      post : Object,
    },
}
</script>

<style>

</style>