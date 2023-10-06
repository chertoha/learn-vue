<template>
  <form class="form" @submit.prevent>
    <h4>Add post</h4>
    <input
      v-bind:value="post.title"
      @input="post.title = $event.target.value"
      class="input"
      type="text"
      placeholder="Post name"
    />
    <input
      v-bind:value="post.text"
      @input="post.text = $event.target.value"
      class="input"
      type="text"
      placeholder="Post text"
    />
    <button class="btn" type="submit" @click="createPost">Add</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        text: "",
      },
    };
  },

  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        text: "",
      };
    },
  },
};
</script>

<style>
.form {
  display: flex;
  flex-direction: column;
  row-gap: 10px;
}

.input {
  padding: 10px 15px;
  width: 100%;
  border: 1px solid rgb(0, 255, 51);
}

.btn {
  padding: 15px;
  width: 200px;
  align-self: flex-end;
}
</style>
