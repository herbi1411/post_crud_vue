<template>
  <div class="container">
    <v-form @submit="onSubmit">
      <v-text-field v-model="title" label="title" required></v-text-field>
      <v-textarea v-model="content" label="content" required></v-textarea>
      <v-btn type="submit" color="primary">등록</v-btn>
    </v-form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PostGenerateView",
  data: function () {
    return {
      title: "",
      content: "",
    };
  },
  methods: {
    onSubmit: function (event) {
      event.preventDefault();
      axios
        .post("http://127.0.0.1:8080/posts", {
          title: this.title,
          content: this.content,
        })
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style></style>
