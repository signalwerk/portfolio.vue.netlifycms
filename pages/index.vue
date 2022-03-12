<template>
  <div>
    <h1>Portfolio</h1>
    <ul>
      <li v-for="post of posts" :key="post.slug">
        <NuxtLink :to="`./portfolio/${post.slug}`"
          >Post {{ post.title }}</NuxtLink
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "IndexPage",

  async asyncData({ $content }) {
    const posts = await $content("portfolio").fetch();

    return {
      posts,
    };
  },
};
</script>
