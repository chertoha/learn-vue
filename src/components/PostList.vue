<template>
  <div class="post-list" v-if="posts.length > 0">
    <h4>Post List</h4>
    <!-- <post-item class="post" v-for="post in posts" :post="post" :key="post.id"
    @remove="$emit("remove", post)" /> -->

    <post-item
      class="post"
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>
  <h3 v-else>List is empty</h3>
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

<style scoped>
.post-list {
  margin-top: 30px;
}
</style>
