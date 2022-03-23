<template>
  <div>
    <h3>Add comment</h3>
    <form @submit.prevent>
      <input v-model="comments.name" type="text" class="form-control"
             placeholder="Enter your name..."/>
      <input v-model="comments.email" type="email" class="form-control my-3"
             placeholder="Enter your email..."/>
      <input v-model="comments.content" type="text" class="form-control"
             placeholder="Enter your message..."/>
      <input type="submit" value="Save" class="btn btn-success my-3" @click="createComment">
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      comments: {
        name: "",
        email: "",
        content: "",
      }
    }
  },
  methods: {
    createComment() {
      this.comments.id = Date.now();
      this.$emit('addComment', this.comments)
      this.comments = {
        name: "",
        email: "",
        content: ""
      }
    }
  }
}
</script>

<style>

</style>