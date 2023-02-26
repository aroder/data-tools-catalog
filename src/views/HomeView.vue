<template>
  <main>
    <div class="categories">
      <h1>Choose a category</h1>
      <ul>
        <li v-for="(category, index) in categories" :key="index">
          <router-link
            :to="{
              name: 'category',
              params: { category: category.toLowerCase() },
            }"
          >
            {{ category }}
          </router-link>
        </li>
      </ul>
    </div>
  </main>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "Categories",
  data() {
    return {
      categories: ["Sports", "Technology", "Food", "Travel"],
    };
  },
});
</script>

<style>
.categories {
  text-align: center;
}

h1 {
  margin-top: 50px;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin: 10px 0;
}

router-link {
  color: #42b983;
  text-decoration: none;
  font-size: 24px;
  font-weight: bold;
}

router-link:hover {
  text-decoration: underline;
}
</style>
