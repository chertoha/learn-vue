<template>
  <!-- <div>
    <div>
        <button @click="addLike">Like</button>
        <button v-on:click="addDisLike">Dislike</button>
    </div>
 <div> Likes quantity {{likes }}</div>
 <div> Likes quantity {{dislikes}}</div>
</div> -->

  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" />

    <!-- <form class="form" @submit.prevent>
      <h4>Add post</h4>
      <input
        v-bind:value="title"
        @input="inputTitle"
        class="input"
        type="text"
        placeholder="Post name"
      />
      <input
        v-bind:value="text"
        @input="inputText"
        class="input"
        type="text"
        placeholder="Post text"
      />
      <button class="btn" type="submit" @click="createPost">Add</button>
    </form> -->

    <!-- <div class="post" v-for="{ id, name, text } in posts">
      <div><strong>Post name:</strong> {{ name }}</div>
      <div><strong>Post text:</strong> {{ text }}</div>
    </div> -->
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
      //   likes: 0,
      //   dislikes: 0,

      //   title: "",
      //   text: "",

      posts: [
        {
          id: Date.now(),
          name: "Post #1 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
        {
          id: Date.now(),
          name: "Post #2 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
        {
          id: Date.now(),
          name: "Post #3 name",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elitPariatur, sint!",
        },
      ],
    };
  },

  methods: {
    // addLike() {
    //   this.likes += 1;
    // },
    // addDisLike() {
    //   this.dislikes += 1;
    // },
    // inputTitle(e) {
    //   this.title = e.target.value;
    // },
    // inputText(e) {
    //   this.text = e.target.value;
    // },
    createPost(post) {
      console.log(post);
      this.posts.push(post);
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

/* .form {
  display: flex;
  flex-direction: column;
  row-gap: 10px;
} */

/* .post {
  margin: 10px 0;
  padding: 15px;
  border: 1px solid red;
} */

/* .input {
  padding: 10px 15px;
  width: 100%;
  border: 1px solid rgb(0, 255, 51);
}

.btn {
  padding: 15px;
  width: 200px;
  align-self: flex-end;
} */
</style>
