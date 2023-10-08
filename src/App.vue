<template>
  <div class="app">
    <h1>Posts page</h1>
    <my-button title="Add post" @click="showDialog" />
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>
    <!-- <post-list :posts="posts" @remove="deletePost" /> -->
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from "./components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
    PostForm,
    PostList,
  },

  data() {
    return {
      dialogVisible: false,

      posts: [
        {
          id: 111,
          title: "Post #1 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
        {
          id: 222,
          title: "Post #2 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
        {
          id: 333,
          title: "Post #3 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
      ],
    };
  },

  methods: {
    createPost(post) {
      // console.log(post);
      this.posts.push(post);
      this.dialogVisible = false;
    },

    removePost(post) {
      // console.log(post.id);

      this.posts = this.posts.filter((p) => p.id !== post.id);
    },

    showDialog() {
      this.dialogVisible = true;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.app {
  margin: 0;
  padding: 30px;
}
</style>
