<template>
  <button class="btn" type="button">{{ this.content }}</button>
</template>

<script>
export default {
  props: {
    content: {
      default: "Button",
      type: String,
    },
  },
};
</script>

<style scoped>
.btn {
  padding: 10px;
  background-color: transparent;
  border: 1px solid green;
  border-radius: 5px;
}
</style>
