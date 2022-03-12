<template>
  <div class="page--portfolio">
    <h1>{{ post.title }}</h1>
    <nuxt-content :document="post" />

    <li class="home__project" v-for="image of post.images" :key="image.image">
      <Project :title="image.title" :image="image.image" />
    </li>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
      post = await $content("portfolio", params.slug).fetch();
      console.log({ post });
    } catch (e) {
      error({ message: "Post not found" });
    }

    return {
      post,
    };
  },
};
</script>

<style>
.home__project-preview {
  width: 400px;
}
</style>