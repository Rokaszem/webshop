<template>
  <div>Filtering</div>
  <ul class="row">
    <li class="item" v-for="item of items" :key="item.id">
      {{ item.title }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      items: [],
    };
  },
  methods: {
    async getData() {
      try {
        let response = await fetch("https://fakestoreapi.com/products?limit=8");
        this.items = await response.json();
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.getData();
  },
};
</script>

<style>
</style>