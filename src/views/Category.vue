<template>
  <div class="category">
    <h1>{{ category }}</h1>
    <p>Here's some content for the {{ category }} category.</p>
  </div>
</template>

<script>
import { defineComponent, computed } from "vue";
import { useRoute } from "vue-router";

export default defineComponent({
  name: "Category",
  setup() {
    const route = useRoute();
    const category = computed(() => route.params.category);

    return {
      category,
    };
  },
});
</script>

<style>
.category {
  text-align: center;
  margin-top: 50px;
}

h1 {
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
}

p {
  font-size: 24px;
  line-height: 1.5;
}
</style>
