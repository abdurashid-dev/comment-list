<template>
  <div class="container py-5">
    <comment-form @addComment="createComment"/>
    <comment-list :comments="comments"/>
  </div>
</template>

<script>
import CommentForm from "./components/CommentForm";
import CommentList from "./components/CommentList"
export default {
  components:{
    CommentForm,
    CommentList
  },
  data() {
    return {
      comments: [
        {id: 1, name: "John", email: "info@gmail.com", content: "lorem ipsum dolar sit amet."},
        {id: 2, name: "Alex", email: "alex@gmail.com", content: "lorem ipsum dolar sit amet."},
        {id: 3, name: "Lucy", email: "lucy@gmail.com", content: "lorem ipsum dolar sit amet."}
      ],
    }
  },
  methods: {
    createComment(comment){
      this.comments.unshift(comment)
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>