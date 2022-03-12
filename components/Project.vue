<!-- Please remove this file from your project -->
<template>
  <div class="project">
    <img v-if="image" class="project__image" :src="image" />
    <p v-if="title" class="project__title">{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: {
    title: {
      type: String,
      default: "",
    },
    image: {
      type: String,
      default: "",
    },
  },
};
</script>

<style>
.project__image {
  width: 300px;
}
</style>