<template>
  <div class="post">
    <div>
      <div><strong>Post name:</strong> {{ post.title }}</div>
      <div><strong>Post text:</strong> {{ post.text }}</div>
    </div>
    <!-- <button type="button" @click="deletePost">Delete</button> -->
    <!-- <my-button content="Delete" @click="$emit("remove", post)" /> -->
    <my-button content="Delete" @click="$emit('remove', post)" />
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  methods: {},
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
