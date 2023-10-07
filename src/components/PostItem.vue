<template>
  <div class="post">
    <div>
      <div><strong>Post name:</strong> {{ post.title }}</div>
      <div><strong>Post text:</strong> {{ post.text }}</div>
    </div>
    <!-- <button type="button" @click="deletePost">Delete</button> -->
    <my-button content="Delete" @click="deletePost" />
  </div>
</template>

<script>
import ByButton from "./UI/MyButton";

export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  methods: {
    deletePost() {
      // console.log(this.post.id);
      this.$emit("delete", this.post.id);
    },
  },
};
</script>

<style>
.post {
  margin: 10px 0;
  padding: 15px;
  border: 1px solid red;
  display: flex;
  justify-content: space-between;
}
</style>
