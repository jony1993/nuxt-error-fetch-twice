<template>
  <div>
    <p v-if="$fetchState.pending">Fetching data....</p>
    <p v-else-if="$fetchState.error">Fetching error...</p>
    <p v-else>Fetching success...</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      post: {},
    };
  },
  async fetch() {
    console.log("Fetching Posts");
    const post = await fetch(
      `https://jsonplaceholder.typicode.com/posts/1`
    ).then((res) => res.json());
    this.post = post;
  },
};
</script>