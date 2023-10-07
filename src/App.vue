<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" @delete="deletePost" />
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
    },

    deletePost(id) {
      console.log(id);
    },
  },
};
</script>

<style scoped>
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
