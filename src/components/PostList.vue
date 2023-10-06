<template>
  <div>
    <h4>Post List</h4>
    <post-item class="post" v-for="post in posts" :post="post" />
  </div>
</template>

<script>
import PostItem from "./PostItem.vue";

export default {
  components: {
    PostItem,
  },

  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
/* .post {
  margin: 10px 0;
  padding: 15px;
  border: 1px solid red;
} */
</style>
