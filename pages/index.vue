<template>
  <div class="page--home">
    <h1>Portfolio</h1>
    <ul class="home__projects">
      <li class="home__project" v-for="post of posts" :key="post.slug">
        <NuxtLink :to="`./portfolio/${post.slug}`">
          <img class="home__project-preview" :src="post.preview" />
          Post {{ post.title }}</NuxtLink
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

<style>
</style>
