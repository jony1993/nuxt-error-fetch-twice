<template>
  <section>
    <h1>
      On this page we set the child component with using a general "component"
    </h1>
    <br />
    <br />
    <component
      :is="child.component"
      v-for="(child, index) in story.content.body"
      :key="index"
    />
    <br />
    <br />
    <nuxt-link to="/">Back home</nuxt-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      story: {
        content: {
          component: "parent-component",
          body: [
            {
              component: "ChildComponentWithFetch",
            },
          ],
        },
      },
    };
  },
};
</script>