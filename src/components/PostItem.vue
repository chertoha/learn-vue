<template>
  <div class="post">
    <div><strong>Post name:</strong> {{ post.title }}</div>
    <div><strong>Post text:</strong> {{ post.text }}</div>
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
};
</script>

<style>
.post {
  margin: 10px 0;
  padding: 15px;
  border: 1px solid red;
}
</style>
